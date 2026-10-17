# Noah's evidence and meeting guide

**CYBR641 · APT29 Variant 1 · SimSpace blue-team exercise**  
Prepared by Noah Gruba · Event activity: October 16, 2026 · Review: October 17, 2026

New to incident response? Start here. No special software or live lab access is needed to read these pages. This folder is separate from [Greg's existing collection](https://github.com/artifical-eerything/range1/tree/main/greg); it does not replace or independently validate his files.

## Choose your path

| Need | Open |
|---|---|
| Understand the case in five minutes | [Findings and six-stage timeline](FINDINGS.md) |
| Lead the next group meeting | [45-minute meeting guide](MEETING-GUIDE.md) |
| Learn how to investigate step by step | [Beginner workflow](WORKFLOW.md) |
| Browse the original evidence pictures | [Evidence gallery](evidence/README.md) |
| Match the work to the assignment | [Assignment checklist and worksheets](ASSIGNMENT-CHECKLIST.md) |
| Understand conflicting classroom notes | [Session context and corrections](SESSION-CONTEXT.md) |
| Understand an unfamiliar term | [Plain-language glossary](TERMS.md) |
| Repeat a narrow, read-only lab search | [Splunk search reference](SEARCHES.md) |
| Verify the source files | [Evidence catalog](evidence/CATALOG.md) and [SHA-256 manifest](evidence/manifest.csv) |

## The story in one paragraph

Charlie Fritz's workstation, **BR-WIN10-1 / 172.16.4.101**, was investigated after a suspicious-behavior report. The same `network_mgr.exe` process resolved `techiefly[.]com`, wrote `C:\Users\Public\WdBoot.exe`, and launched WdBoot as SYSTEM. Discovery, audit/firewall change commands, staging and archive commands followed. Two corresponding HTTP POSTs to `olapdatabase[.]com` returned status 200, strongly supporting file-upload/exfiltration activity. Exact uploaded contents, the initial access method and a separate successful privilege-escalation step were not established by this collection.

The scenario is **APT29-inspired and assume-breach** according to the assignment. That context is not independent proof of an actor, a technique, or an initial-access path.

## Read every claim with one of these labels

- **Observed:** directly present in a screenshot or supplied log record.
- **Inferred:** an explanation supported by observations but not directly demonstrated.
- **Unknown:** not established by the evidence available here.
- **Context:** assignment/debrief information, not a substitute for technical evidence.

For example: a DNS lookup is observed; a download from that domain is an inference until a transfer is evidenced.

## Sharing and safety

Included pictures are unchanged copies, with their original EV numbers. Credential-bearing pictures and a credential-bearing pasted log remain private, not blurred or silently edited. The catalog explains omissions. The original topology screenshot EV-003 was not available; it is not fabricated. Unnecessary raw configuration text is also kept local.

Some images contain historical conclusions or automated technique labels that were later revised. **Use the captions and current findings to interpret them.** Never execute command strings copied from evidence. Do not visit the suspicious domains. Live lab actions require the instructor's current authorization; this package does not authorize containment, account changes, RDP or proxy reconfiguration.

This is a shared evidence/study resource, **not a completed individual submission**. Each student must supply their own analysis, actual contributions and professional judgment. AI-assisted organization is disclosed in the assignment checklist.
