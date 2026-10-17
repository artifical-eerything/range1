# Findings: what the evidence supports

[Start here](README.md) · [Meeting guide](MEETING-GUIDE.md) · [Evidence catalog](evidence/CATALOG.md)

## Scope and conclusion

The reviewed workstation is **BR-WIN10-1 (172.16.4.101)**, associated with the reporting user Charlie / `charley.fritz`. The assignment identifies an APT29-inspired assume-breach scenario. Independent actor attribution and initial intrusion prevention are not established by that scenario description.

The evidence supports WdBoot placement/execution as SYSTEM, subsequent discovery and defense-change commands, staging/archive commands, and two strongly correlated outbound upload transactions. It does **not** establish the exact uploaded contents, an independently verified initial download, a separate successful escalation, persistence, or that the host was isolated.

## Six significant stages

Times are October 16, 2026, in the range's Eastern-aligned display unless marked UTC. The proxy explicitly records UTC−04:00. Raw event UTC values take precedence; the Splunk account setting was not independently inspected.

| Stage | Action and evidence | Result / confidence | Documented defender response and operational effect |
|---|---|---|---|
| 1. Local payload chain and check-in | At **16:57:49.459 UTC**, network_mgr resolves techiefly[.]com. The same GUID writes WdBoot at 12:57:50 and launches it as SYSTEM at 12:57:59. Swipeservice update/registration GETs also appear at 12:57:59. EV-031/032, EV-028, EV-027, EV-018, EV-014, EV-029. | Local write/launch observed, high confidence. Download source and specific request process unverified; check-in/C2 interpretation is an inference. | Analysts later linked process/DNS/file/proxy records. Activity exposed; no demonstrated interruption from that analysis. |
| 2. Defense-change commands | Detailed Tracking audit disable at 12:59:00–01. Firewall add commands at 12:59:32 specify outbound UDP **block** rules for **local ports 137 and 53**. EV-041; audit parent screenshot EV-025 remains private. | Commands/processes observed. Exact initial policy/rule state and resulting suppression not independently captured. | Commands were documented; no defender policy change is claimed. Sysmon records remained available for investigation. |
| 3. Discovery | Disk, processes, user/session, scheduled-task and service queries run around 13:01–13:04, with output redirections. EV-013, EV-017, EV-037. | Query execution/command text supported. Actual output contents not recovered. `schtasks /query` is enumeration, not persistence. | Analysts traced parent processes and distinguished provisioning from suspicious activity. This improves attribution, not proof of prevention. |
| 4. Staging and archiving | A user-derived Temp `.tmp` directory is requested at 13:00:03; Compress-Archive targets `.tmp.zip` at 13:04:53–54. EV-036/037. | Intended staging/archive observed. Successful archive completion and contents remain unknown. One WMI redirection uses a different variable. | Targeted searches/collections attempted; artifacts not recovered. No proof of deletion from empty results. |
| 5. Two uploads | A random user-file selection command precedes the **13:05:26** double-slash POST. A ZIP selection command precedes the **13:05:57** single-slash POST. Both target olapdatabase[.]com and return HTTP 200. EV-033, EV-035, EV-036, EV-042. | HTTP transactions observed, high confidence. Strong support for file-upload/exfiltration activity; actual filename/data and remote storage not verified. | Analysts correlated two distinct upload sources and verified byte definitions. No blocking or containment demonstrated. |
| 6. Reversal commands and investigation limits | Audit re-enable at 13:06:27–28, followed by deletion of the named firewall rules at 13:07:28–29. Later auditpol/netsh termination excerpts show exit 0. EV-041. File searches and PCAP attempts did not recover contents. | Completion supported for later commands, but full state not independently checked. Sequence is consistent with reversal/cleanup; motive inferred. | Investigators corrected a wrong time filter, suspended a reportedly faulty tool and recorded unresolved questions. No outcome rating is assigned for the entire class without classmates' action/result evidence. |

The approximately ten-minute visible sequence is not proof that all incident activity ended at 13:07:28. A direct-child process search's last matching creation is not an executable's exit time. EV-034.

## Upload sizes: what was actually measured

The acquired local configuration defines `bytes_in=%>st`, `bytes_out=%<st` and `bytes=%st`, and selects that format for the access log. Official Squid documentation identifies these as request bytes received from the client, reply bytes sent to the client, and their combined traffic. EV-049; [Squid logformat reference](https://www.squid-cache.org/Doc/config/logformat/).

| Proxy event time, UTC−04:00 | Request received from workstation | Reply to workstation | Command correlation |
|---|---:|---:|---|
| 13:05:26 | 77,908 bytes | 284 bytes | Random user-profile file selection, double-slash URL. |
| 13:05:57 | 32,494 bytes | 284 bytes | Intended reconnaissance ZIP selection, single-slash URL. |

These request counters include HTTP overhead. **They are not exact stolen-file sizes.** The acquired config matches the logged fields and arithmetic, but its historical loaded state was not independently verified. The shown access-log format records metadata and selected headers, not upload bodies.

## Three conclusions for discussion

| Conclusion | Interpretation and alternative | Limitation and confidence |
|---|---|---|
| network_mgr writes and launches WdBoot | Same GUID links the events; this is stronger than matching names. An exercise-controlled process can implement this chain, so it does not establish original attacker entry. | High for local sequence; original access unknown. EV-028/018/031. |
| POST activity is consistent with exfiltration | Matching commands, times, URLs and PowerShell user-agent support uploads. A lab emulation or unrelated permitted POST is an alternative if considered without the command context. | High for transactions; strong inference for upload activity; exact data unknown. EV-033/035/036/042. |
| Defense changes were requested, then reversed | Commands show audit disable/enable and firewall block-rule add/delete. This may be emulated evasion/cleanup, not evidence of global logging failure or rules allowing exfiltration. | High for command observations, lower for complete operational effect. EV-041. |

## Important non-findings

- **No confirmed Chrome download:** DNS immediately preceding a file write is not a browser-download record.
- **No demonstrated 30-second beacon cadence** in the selected records. Do not infer periodicity from two same-second GETs.
- **No proven domain-admin credential theft or separate escalation:** WdBoot is already SYSTEM before the supplied-credential relaunch attempt. Local Administrator and domain administrator are not interchangeable.
- **No scheduled-task persistence:** the observed command queries tasks; it does not create one.
- **No APT29 attribution from rule names:** the scenario is APT29-themed; strings such as apt29-rule-1 are not independent attribution evidence.
- **No proven full environment containment:** the user directed a single-workstation scope; one filename-based query only supports that view of matching events.
- **No deletion conclusion:** live-file recovery and a deletion-event query returned nothing. That does not prove deletion or failed creation.
- **No useful negative network conclusion from Security Onion:** job 1002 used the wrong hours; job 1003's correct filter is visible but its empty packet table was user-reported. The class was reportedly told the tool was not working correctly. EV-043–046.

## What remains to complete an individual report

The group needs actual evidence of any Blue Team stop/contain/mitigate actions, a participation/completion screenshot if provided, individual contributions, and an independently defended operational outcome. Do not invent these from Noah's detection-only record. See the [assignment checklist](ASSIGNMENT-CHECKLIST.md).
