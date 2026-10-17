# Evidence gallery

[Noah / Start here](../README.md) · [Meeting guide](../MEETING-GUIDE.md) · [Catalog](CATALOG.md)

**36 unchanged screenshots and 6 supporting text records** are included. Four credential-bearing screenshots and one credential-bearing log stay private. EV-003 is unavailable; the partial raw configuration EV-048 stays local. No redacted or AI-generated replacement images are used.

Follow chapters 1–4 for the main story. Chapters 5–6 are a reference for limitations and background—not extra attack stages. Click a picture to inspect the original resolution.

| Chapter | Purpose |
|---|---|
| [1. Find the user, workstation and useful sources](01-orientation.md) | 8 screenshots, each with an observation and a limit. |
| [2. Link DNS, file placement and execution](02-local-sequence.md) | 6 screenshots, each with an observation and a limit. |
| [3. Inspect execution, discovery and check-in evidence](03-execution-and-discovery.md) | 5 screenshots, each with an observation and a limit. |
| [4. Corroborate uploads and interpret the proxy](04-uploads-and-proxy.md) | 4 screenshots, each with an observation and a limit. |
| [5. Understand recovery limits and tool problems](05-recovery-and-tool-limits.md) | 7 screenshots, each with an observation and a limit. |
| [6. Background checks and revised leads](06-background-and-rejected-leads.md) | 6 screenshots, each with an observation and a limit. |

## Supporting records

These supplied text excerpts are evidence to read, not scripts to execute. They are not original EVTX/PCAP exports and may explicitly omit lines.

- [EV-029 — Proxy rows around payload placement](records/EV-029_brwin10-1_proxy-drop-window.txt)
- [EV-030 — Pasted DNS results](records/EV-030_techiefly-dns-pasted-results.txt)
- [EV-031 — Complete Sysmon DNS event](records/EV-031_techiefly-sysmon-dns-pasted-event.txt)
- [EV-036 — Archive and two upload selections](records/EV-036_archive-and-upload-pasted-events.txt)
- [EV-037 — Discovery output staging commands](records/EV-037_recon-staging-pasted-events.txt)
- [EV-041 — Audit and firewall command sequence](records/EV-041_audit-firewall-pasted-events.txt)

## Integrity and provenance

Included files are byte-identical to the numbered private evidence collection, and their SHA-256 values match the original register. [manifest.csv](manifest.csv) records all 49 EV IDs, including omissions. Early acquisition notes contain approximate or unverified timezone labels; they are preservation metadata, not event timestamps. A hash proves matching bytes, not authenticity, complete logs or analytical correctness.

[Sharing and withheld evidence](SHARING.md) explains the boundary. Current captions supersede historical automated labels/assumptions in the unchanged pictures.
