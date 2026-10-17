# Plain-language glossary

[Start here](README.md)

| Term | Meaning in this case |
|---|---|
| Artifact | A saved item that helps explain activity: screenshot, event text, file metadata or configuration excerpt. |
| EV number | A stable identifier such as EV-028. It is not necessarily the time order of attacker activity. |
| Host / endpoint | A computer; BR-WIN10-1 is the workstation investigated. |
| SIEM / Splunk | A place to search collected logs from multiple systems. An alert there is a lead, not automatic proof. |
| Sysmon | Endpoint telemetry used here for process creation, file creation and DNS events. |
| Parent / child process | A program that starts another program. The relationship helps trace execution. |
| Process GUID | An identifier for a process instance; stronger for correlation than a reused filename alone. |
| SYSTEM | A powerful local Windows execution context. It does not automatically mean domain administrator. |
| DNS | Resolving a name to an address. A DNS response is not a file download. |
| Proxy | A server handling a client's web requests; the logs here identify site-proxy and Squid. |
| HTTP POST | A web request that can carry data. Method alone does not establish malicious exfiltration. |
| HTTP 200 | A successful HTTP response code, not proof of exactly what the remote server retained. |
| C2 / check-in | Communication associated with controlling or reporting from an implant; specific intent must be supported. |
| Discovery | Queries to learn about users, processes, services, disks or tasks. |
| Staging | Preparing data in a location before later use or transfer. |
| Archive | A container such as a ZIP; a command requesting one is not proof its contents were successfully created. |
| Exfiltration | Unauthorized data removal. Here, commands plus POSTs strongly support upload activity; exact data is unknown. |
| PCAP | Recorded packets. Logs and packet contents have different retention and visibility limits. |
| SHA-256 | A fingerprint of the saved file's bytes. It helps detect changes; it does not certify truth or completeness. |
| ATT&CK | A vocabulary for behavior. A technique label does not prove the behavior happened or name an actor. |
| Assume breach | Begin with a foothold already assumed, then evaluate post-compromise behavior and defense. |
| Containment | An action limiting attacker access or spread. Finding a host or opening a case is not isolation. |
| Negative result | A check returned no matches. Its meaning depends on scope, filter correctness and source reliability. |

Technical interpretation references are provided in the findings and assignment checklist. This is a study aid, not a replacement for product documentation.
