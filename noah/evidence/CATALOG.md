# Evidence catalog — every EV number

[Gallery](README.md) · [Sharing rules](SHARING.md) · [SHA-256 manifest](manifest.csv)

EV numbers are source identifiers, not figure numbers or attacker time order. No private original is embedded or linked to a public copy.

| EV | Description | Access / current interpretation |
|---|---|---|
| [EV-001](01-orientation.md#ev-001) | Available log sources, page 1 | Unchanged screenshot. Log volume and source availability do not establish compromise. |
| [EV-002](01-orientation.md#ev-002) | Available log sources, page 2 | Unchanged screenshot. An index count is not the number of attacker actions. |
| EV-003 | Topology screenshot not available | MISSING — original screenshot unavailable. No replacement or fabricated image is supplied. |
| [EV-004](01-orientation.md#ev-004) | Risk alerts prioritize a workstation | Unchanged screenshot. Risk ranking is a triage lead, not proof that every listed host is compromised. |
| [EV-005](01-orientation.md#ev-005) | Workstation process-event volume | Unchanged screenshot. These are not 7,575 malware launches or proof of continued attack through the final displayed hour. |
| [EV-006](06-background-and-rejected-leads.md#ev-006) | Early Security Onion alert overview | Unchanged screenshot. It does not show a clean network; the tool was later reported to be malfunctioning. |
| [EV-007](06-background-and-rejected-leads.md#ev-007) | SSH alert drilldown | Unchanged screenshot. No malicious actor or successful access is established; this is not part of the confirmed payload chain. |
| [EV-008](01-orientation.md#ev-008) | Account activity across hosts | Unchanged screenshot. Account activity alone neither identifies the sole workstation nor proves lateral movement; user report and additional context matter. |
| [EV-009](01-orientation.md#ev-009) | Reporting-user account lookup | Unchanged screenshot. This does not identify an attacker-created account or prove credential theft. The credential prompt shown does not expose the password. |
| [EV-010](01-orientation.md#ev-010) | An activity-count lead, not a finding | Unchanged screenshot. The displayed table is not the result of the unexecuted query in the bar, and a count spike is not proof of credential abuse. |
| [EV-011](01-orientation.md#ev-011) | Alert-rule breakdown | Unchanged screenshot. An automated detection is a reason to inspect process evidence, not a completed maliciousness decision. |
| EV-012 | Recon table containing a credential | PRIVATE — credential-bearing original withheld. Kept private; no image bytes are included in this repository. |
| [EV-013](03-execution-and-discovery.md#ev-013) | Discovery tools with non-CMD parents | Unchanged screenshot. Parent context is needed; command names alone are not proof of malicious use. |
| [EV-014](03-execution-and-discovery.md#ev-014) | Workstation-registration HTTP request | Unchanged screenshot. This supports a check-in hypothesis, not unique endpoint-process attribution, beacon cadence or real-world actor attribution. |
| EV-015 | Java/CMD table containing a credential | PRIVATE — credential-bearing original withheld. Kept private; no image bytes are included in this repository. |
| [EV-016](06-background-and-rejected-leads.md#ev-016) | Visible routine startup commands | Unchanged screenshot. Those visible rows are not evidence of initial attacker entry; they also do not exclude every other action in the period. |
| [EV-017](03-execution-and-discovery.md#ev-017) | WdBoot to PowerShell and discovery tools | Unchanged screenshot. The UI labels schtasks as T1053, but the later command text is /query. Do not claim task persistence from that automatic label. |
| [EV-018](02-local-sequence.md#ev-018) | WdBoot execution as SYSTEM | Unchanged screenshot. It does not establish how the original foothold was obtained. Recheck any executable hash transcription against this source before using it as an exact IOC. |
| [EV-019](02-local-sequence.md#ev-019) | Earlier network_mgr executions | Unchanged screenshot. Explorer parentage does not prove a manual malicious-file double-click; the range provisioning context matters. |
| [EV-020](06-background-and-rejected-leads.md#ev-020) | Early proxy search, partial display | Unchanged screenshot. The visible rows do not prove a successful payload download or exclude another route/time. |
| [EV-021](06-background-and-rejected-leads.md#ev-021) | Early proxy search summarized | Unchanged screenshot. This window does not demonstrate delivery; it does not rule out delivery outside that scope. |
| EV-022 | Timeline view containing a credential | PRIVATE — credential-bearing original withheld. Kept private; no image bytes are included in this repository. |
| [EV-023](06-background-and-rejected-leads.md#ev-023) | Puppet maintenance context | Unchanged screenshot. The user identified Puppet as lab provisioning. Do not count this maintenance loop as attacker persistence or the initial access path. |
| EV-024 | Credential-bearing script-block text | PRIVATE — credential-bearing original withheld. Kept private; neither the text nor its credential is included. |
| EV-025 | WdBoot child commands containing a credential | PRIVATE — credential-bearing original withheld. Kept private. WdBoot was already SYSTEM; this does not independently prove successful escalation or domain-admin theft. |
| [EV-026](02-local-sequence.md#ev-026) | Pre-existing network_mgr file metadata | Unchanged screenshot. Metadata does not establish original delivery, trustworthiness or an attacker foothold. |
| [EV-027](02-local-sequence.md#ev-027) | WdBoot file metadata | Unchanged screenshot. A file timestamp is not a network-transfer record or independent proof that timestamps were not manipulated. |
| [EV-028](02-local-sequence.md#ev-028) | The process that wrote WdBoot | Unchanged screenshot. A file writer is not necessarily the original intrusion vector or proof of a particular source download. |
| [EV-029](records/EV-029_brwin10-1_proxy-drop-window.txt) | Proxy rows around payload placement | Supplied text record. The pasted table lacks source-IP columns; association depends on query context and EV-014. Requests occur after local file creation. |
| [EV-030](records/EV-030_techiefly-dns-pasted-results.txt) | Pasted DNS results | Supplied text record. Resolver traffic does not show compromised DNS/DC servers or a payload transfer. Security Onion reliability was later questioned. |
| [EV-031](records/EV-031_techiefly-sysmon-dns-pasted-event.txt) | Complete Sysmon DNS event | Supplied text record. A DNS query is not proof of a Chrome download or successful connection. |
| [EV-032](02-local-sequence.md#ev-032) | Screenshot of the DNS event | Unchanged screenshot. Use original UtcTime rather than rounded/ingested display time; the source-domain claim remains a hypothesis. |
| [EV-033](03-execution-and-discovery.md#ev-033) | ZIP upload command in parsed logs | Unchanged screenshot. The image alone lacks complete event time/parent/output context and does not reveal actual archive contents. Never execute this command. |
| [EV-034](03-execution-and-discovery.md#ev-034) | Filename-based workstation scope | Unchanged screenshot. This is not 17 malware copies, proof of isolation, a complete environment clearance or total runtime. |
| [EV-035](04-uploads-and-proxy.md#ev-035) | Two POSTs, two responses | Unchanged screenshot. Exact uploaded contents and storage on the remote server are unknown. Request/reply counter meanings are explained by EV-049. |
| [EV-036](records/EV-036_archive-and-upload-pasted-events.txt) | Archive and two upload selections | Supplied text record. Omitted event lines and absent command output prevent identification of the actual random filename, resolved profile and ZIP contents. |
| [EV-037](records/EV-037_recon-staging-pasted-events.txt) | Discovery output staging commands | Supplied text record. Commands are intended outputs, not recovered files. A WMI redirection uses a different variable, and schtasks is enumeration. |
| [EV-038](05-recovery-and-tool-limits.md#ev-038) | Analyst FileFinder search parameters | Unchanged screenshot. This is analyst collection code, not malware source; configuration alone is not a recovered artifact. |
| [EV-039](05-recovery-and-tool-limits.md#ev-039) | FileFinder returned no artifacts | Unchanged screenshot. The cropped view lacks the flow ID/completion state; absence of a recovered file is not proof of deletion or failed creation. |
| [EV-040](05-recovery-and-tool-limits.md#ev-040) | No matching deletion events | Unchanged screenshot. This does not establish comprehensive deletion coverage, non-deletion, or whether the files ever existed. |
| [EV-041](records/EV-041_audit-firewall-pasted-events.txt) | Audit and firewall command sequence | Supplied text record. Multiple log entries can describe one action. Full policy/rule state is not independently verified; rule names do not attribute an actor. |
| [EV-042](04-uploads-and-proxy.md#ev-042) | Full proxy POST event view | Unchanged screenshot. Metadata does not contain an uploaded filename or request body; user-agent is not unique process attribution. |
| [EV-043](05-recovery-and-tool-limits.md#ev-043) | Completed PCAP jobs | Unchanged screenshot. Completion does not mean packets were found. Queue/completion dates are not the traffic-filter date range. |
| [EV-044](05-recovery-and-tool-limits.md#ev-044) | Job 1002 returned zero packets | Unchanged screenshot. Its filter was later shown to exclude the uploads. This cannot test packet availability at the incident time. |
| [EV-045](05-recovery-and-tool-limits.md#ev-045) | The incorrect time filter was identified | Unchanged screenshot. That is a 24-hour interval beginning after the 13:05 uploads, not both complete calendar days. |
| [EV-046](05-recovery-and-tool-limits.md#ev-046) | Corrected PCAP job bounds | Unchanged screenshot. Its empty packet result was reported by the user, not visible in this crop. Security Onion was reportedly faulty; do not infer absent traffic. |
| [EV-047](04-uploads-and-proxy.md#ev-047) | Proxy log directory through SFTP | Unchanged screenshot. A directory listing does not establish contents, exact truncated file sizes, event coverage or independently verified SSH identity. |
| EV-048 | Partial configuration paste kept local | LOCAL ONLY — partial raw configuration. Not published because the full default/configuration text adds little to the beginner gallery. Its absence of logging directives was not a full-file finding. |
| [EV-049](04-uploads-and-proxy.md#ev-049) | Logging format and byte directions | Unchanged screenshot. Request totals include HTTP overhead, not exact file sizes. Historical loaded configuration was not separately proved. Old analyst path errors visible above are not victim deletion evidence. |
