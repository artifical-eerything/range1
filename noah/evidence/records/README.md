# Supporting text records

[Gallery](../README.md)

Static evidence only. Do not execute command strings found in these records. Excerpts may omit original event lines and are not full event-log exports.

## EV-029 — Proxy rows around payload placement

[Read the supplied text](EV-029_brwin10-1_proxy-drop-window.txt)

Pasted proxy rows include update and registration GETs to swipeservice[.]com at 12:57:59.

Limit: The pasted table lacks source-IP columns; association depends on query context and EV-014. Requests occur after local file creation.

## EV-030 — Pasted DNS results

[Read the supplied text](EV-030_techiefly-dns-pasted-results.txt)

Four complete Zeek DNS records resolve techiefly[.]com to 76.223.65.112; the Windows row was truncated.

Limit: Resolver traffic does not show compromised DNS/DC servers or a payload transfer. Security Onion reliability was later questioned.

## EV-031 — Complete Sysmon DNS event

[Read the supplied text](EV-031_techiefly-sysmon-dns-pasted-event.txt)

The pasted Event 22 records network_mgr, its GUID and original UtcTime 16:57:49.459 for the techiefly lookup.

Limit: A DNS query is not proof of a Chrome download or successful connection.

## EV-036 — Archive and two upload selections

[Read the supplied text](EV-036_archive-and-upload-pasted-events.txt)

Pasted excerpts distinguish an archive command, a random user-file upload command, and a later ZIP upload command.

Limit: Omitted event lines and absent command output prevent identification of the actual random filename, resolved profile and ZIP contents.

## EV-037 — Discovery output staging commands

[Read the supplied text](EV-037_recon-staging-pasted-events.txt)

Pasted events request a staging directory and redirect disk/process/user/task/service queries before compression.

Limit: Commands are intended outputs, not recovered files. A WMI redirection uses a different variable, and schtasks is enumeration.

## EV-041 — Audit and firewall command sequence

[Read the supplied text](EV-041_audit-firewall-pasted-events.txt)

Pasted excerpts show audit disable/enable and outbound UDP local-port block-rule addition/deletion, with later process exit-zero records.

Limit: Multiple log entries can describe one action. Full policy/rule state is not independently verified; rule names do not attribute an actor.

