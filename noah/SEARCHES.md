# Read-only Splunk search reference

[Workflow](WORKFLOW.md) · [Findings](FINDINGS.md)

Only use these in the authorized range. They search existing logs; they do not run the commands appearing inside evidence. Replace the entire search field. These examples use the range's Eastern-aligned display times, not the analyst laptop's Pacific time. Confirm the account timezone first. Keep friendly traffic to/from 10.10.3.0/24 out of conclusions.

## 1. What wrote WdBoot?

```spl
index=windows host=br-win10-1 EventCode=11
earliest="10/16/2026:12:57:30" latest="10/16/2026:12:58:10"
"WdBoot.exe"
| table _time Image TargetFilename ProcessGuid
| sort 0 _time
```

Compare the writer GUID with the parent GUID in the payload's process creation. Expected evidence: EV-028 and EV-018. Do not infer a network source from a file-create event alone.

## 2. Which process resolved techiefly?

```spl
index=windows host=br-win10-1 EventCode=22
earliest="10/16/2026:12:57:00" latest="10/16/2026:12:59:00"
"techiefly.com"
| table _time UtcTime Image ProcessGuid QueryName QueryResults
| sort 0 _time
```

Use original UtcTime for fine-grained ordering. Expected evidence: EV-031/032. A match is DNS, not a confirmed Chrome download.

## 3. Open the original POST records

```spl
index=proxy "olapdatabase.com" src_ip="172.16.4.101"
earliest="10/16/2026:13:05:00" latest="10/16/2026:13:06:00"
NOT (src_ip="10.10.3.*" OR dest_ip="10.10.3.*")
```

Choose Events, expand both records and preserve original fields. Expected evidence: EV-042. bytes_in is request traffic received by the proxy, not exact file size; see EV-049.

## 4. Audit and firewall command sequence

```spl
index=windows host=br-win10-1
earliest="10/16/2026:12:58:00" latest="10/16/2026:13:10:00"
("auditpol" OR "netsh" OR "apt29-rule-1" OR "apt29-rule-2")
| sort 0 _time
```

Multiple logs can describe one action. Expected evidence: EV-041. Separate actual commands from module-loading text, WinRM rule queries and unrelated management activity. Do not expose credentials in new screenshots.

## What not to repeat

The staging-file recovery branch is closed with a limitation; missing artifacts were not proved deleted. Security Onion was reportedly malfunctioning. Repeating the same PCAP request or empty file query will not make the conclusion stronger. A corrected invalid filter is a reason to retry once; a genuinely different evidence source is a reason to reopen.
