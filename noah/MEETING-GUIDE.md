# Next meeting: follow the evidence together

[Start here](README.md) · [Findings](FINDINGS.md) · [Gallery](evidence/README.md)

**Suggested length: 45 minutes.** The goal is a shared understanding of what happened, what is uncertain, and what each student still needs for the individual assignment. This is a discussion/review meeting, not a live containment exercise.

## Before the meeting

1. Read the one-paragraph story in [README](README.md).
2. Open [FINDINGS](FINDINGS.md) and [the gallery](evidence/README.md) in two browser tabs.
3. Bring one question. No one needs to memorize tool names or commands.
4. The facilitator checks that figures open and keeps credential-bearing originals off shared/public screens.

## Simple roles

- **Facilitator:** keeps time and asks the questions below.
- **Evidence reader:** points to the exact field or line supporting a claim.
- **Recorder:** writes decisions and unresolved questions with EV numbers.
- **Skeptic/time checker:** asks what else could explain it and checks timezones.

Small groups can combine roles. Rotate the evidence reader so newer members practice.

## Agenda

| Minutes | Question | Material to open | What the group should produce |
|---|---|---|---|
| 0–5 | What was the assignment, and what was already assumed? | [Assignment checklist](ASSIGNMENT-CHECKLIST.md), [session context](SESSION-CONTEXT.md) | Agree: assume-breach, evidence-based analysis, not actor attribution from a scenario label. |
| 5–10 | Which user and workstation were investigated? | [Orientation gallery](evidence/01-orientation.md): EV-008, EV-009; EV-004 as an alert lead | Name the workstation. Explain why high alert counts alone are not proof. |
| 10–18 | Who created and launched WdBoot? | [Local sequence](evidence/02-local-sequence.md): EV-032 → EV-028 → EV-027 → EV-018 | One sentence linking DNS, file write and execution; one sentence saying what it does not prove. |
| 18–25 | What ran afterward? | [Execution/discovery](evidence/03-execution-and-discovery.md), [EV-037 text](evidence/records/EV-037_recon-staging-pasted-events.txt), [EV-041 text](evidence/records/EV-041_audit-firewall-pasted-events.txt) | Separate discovery, archive requests and audit/firewall commands from their unverified outcomes. |
| 25–32 | What evidence supports upload activity? | [Uploads/proxy](evidence/04-uploads-and-proxy.md): EV-033, EV-035, EV-042, EV-049 | Distinguish two upload selections; explain request bytes versus file bytes. |
| 32–37 | What could not be recovered, and why does that matter? | [Recovery limits](evidence/05-recovery-and-tool-limits.md): EV-039, EV-040, EV-045, EV-046 | State the missing contents, the wrong first time window, and reported Security Onion problem without claiming no traffic. |
| 37–43 | How do we turn this into an individual analysis? | [Assignment worksheets](ASSIGNMENT-CHECKLIST.md) | Choose three conclusions, two actual defensive decisions, one control, and one rejected ATT&CK mapping. |
| 43–45 | What happens next, and who owns it? | Decision log below | Assign only evidence gaps required for the assignment; stop repeated empty searches. |

## Eight suggested report figures — not eight additional tasks

These are candidates, not a mandatory shared figure set. Students select approximately 6–8 artifacts that support their own reasoning; renumber them as Figure 1, Figure 2, etc. in each report. EV numbers remain stable source identifiers.

| Candidate figure | Source | What to explain |
|---|---|---|
| 1 | EV-028 | The executable that wrote WdBoot and its process GUID. |
| 2 | EV-018 | WdBoot execution as SYSTEM and its parent. |
| 3 | EV-032 | DNS before file creation; why that is not a proven download. |
| 4 | EV-017 | PowerShell/discovery chain; why the UI's scheduled-task label is not proof of persistence. |
| 5 | EV-033 | The ZIP upload command as static evidence, not a verified ZIP inventory. |
| 6 | EV-042 | Two POST requests, source/destination, status, timezone and user-agent. |
| 7 | EV-049 | Byte-counter definitions and why request size is not exact stolen-file size. |
| 8 | EV-046 or an excerpt of EV-041 | A visibility limitation or audit/firewall command sequence. EV-046's empty packet result was user-reported, not visible in that crop. |

Do not use the full gallery as the body of the report. Additional material belongs in an appendix only when it supports analysis. A participation/completion screen is still needed for Appendix A if provided by the range; it is not included in this collection.

## Ask these four questions at every figure

1. What exactly is visible? Point to a field, timestamp, path or log line.
2. What does that most strongly suggest?
3. What else could explain it, or what is missing?
4. Did any documented defender action prevent, delay, expose or contain it—or was it only observed afterward?

## Decision log — fill during the meeting

| Question / decision | Evidence ID | Observed, inferred or unknown? | Owner | Needed next / stopping condition |
|---|---|---|---|---|
| Which actual containment or mitigation actions, if any, did classmates perform? | To supply | Unknown in Noah's record | Assign in meeting | Obtain actual action/result evidence; do not invent a group outcome. |
| Which activity can be independently mapped to ATT&CK? | See checklist | Review candidates | Each student | Verify current MITRE page and artifact, not scenario membership. |
| What warrants reopening a closed recovery branch? | EV-038–046 | No bodies recovered | Assign only if necessary | A genuinely new authorized source, not an equivalent empty query. |

## Close the meeting with a 30-second summary

The group should be able to state the observed sequence, one strong inference, one important unknown, and one actual defensive decision with its measured or unmeasured effect. Nobody should leave believing that an alert, a successful command, an actor label and a prevented attack are the same thing.
