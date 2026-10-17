# Assignment checklist and meeting worksheets

[Start here](README.md) · [Meeting guide](MEETING-GUIDE.md) · [Findings](FINDINGS.md)

This is a planning aid based on the supplied CYBR641 Lab 6 / Session 8 assignment, not a completed individual report. The instructor's complete current instructions control. Evidence can be shared; each student's reasoning, decisions, contribution and reflection must remain their own.

## Build the report around these ten parts

| Part | Required work | What this collection helps with | What each student still supplies |
|---|---|---|---|
| 1. Operational reconstruction | Approximately 4–6 stages: action, evidence, defender response, result, effect. | [Six-stage reconstruction](FINDINGS.md). | Actual group response evidence; distinguish later analysis from live intervention. |
| 2. Evidence and confidence | Three conclusions with evidence, interpretation, alternative, limitation and confidence. | Three discussion conclusions in Findings. | Independent reasoning and confidence justification. |
| 3. ATT&CK analysis | 3–5 observed behaviors plus one rejected mapping, verified against current MITRE. | Candidate table below. | Validate and defend mappings; a scenario label is not proof. |
| 4. Defensive decisions | Two actual decisions, situation/evidence/objective/result/effect/risk/alternative/judgment. | Decision worksheet below. | Personally or collectively documented decisions, not hypothetical actions presented as facts. |
| 5. Defensive control | One capability: action → control → observed effect → remaining risk. | Sysmon exposure and proxy visibility are supported leads. | Explain the measured effect and limitations; do not equate detection with prevention. |
| 6. Assume-breach and constraints | Explain what assumed compromise permits/cannot evaluate; one important boundary. | Scenario context, detection-only boundary, faulty Security Onion, provisioning context. | Explain how the selected constraint affected judgment. |
| 7. Operational outcome | Evaluate Stop / Contain / Mitigate; defend one required outcome rating. | Detected behavior and explicit unknowns. | Evidence for actual stopped/contained/mitigated actions; class outcome is not established here. |
| 8. After-action assessment | What worked, failed, changed, visibility gap; two prioritized, testable recommendations. | Time-filter correction, byte-schema validation and unrecovered contents. | Operational implications and independently selected recommendations. |
| 9. Individual contribution | Actual personal work and conclusions, including revisions. | Stable source IDs identify Noah's contributed artifacts. | Each student's own actions; do not rank classmates or claim another person's work. |
| 10. Reflection | 3–5 sentences about challenge, investigation, revised assumption and lesson. | Several concrete examples are available. | A personal technical reflection, not copied group prose. |

## ATT&CK candidates — reviewed October 17, 2026

These are evidence-supported candidates for discussion, not instructions to assign every technique. Each student must validate the live MITRE entry at submission and explain contrary evidence. Mapping confidence is not the same as command-success or operational-outcome confidence.

| Observed behavior | Tactic / candidate | Supporting artifact and rationale | What could weaken it / confidence |
|---|---|---|---|
| WdBoot-associated PowerShell execution and commands | Execution — [T1059.001 PowerShell](https://attack.mitre.org/techniques/T1059/001/) | EV-017, EV-037 and EV-041 show PowerShell-related process/script evidence. | Unrelated administrative PowerShell can look similar without parent/command context. High for observed execution in this chain. |
| Querying logged-on users/sessions | Discovery — [T1033 System Owner/User Discovery](https://attack.mitre.org/techniques/T1033/) | EV-013/017 and EV-037 show quser/query-user behavior. | Legitimate administration is an alternative if chain context is removed. High for query behavior. |
| Listing processes | Discovery — [T1057 Process Discovery](https://attack.mitre.org/techniques/T1057/) | EV-013 and EV-037 show tasklist /v and an intended output path. | A staged command not executed, or unrelated management activity, would weaken the chain. High for observed query; output contents not recovered. |
| Archiving staged data with a built-in utility | Collection — [T1560.001 Archive via Utility](https://attack.mitre.org/techniques/T1560/001/) | EV-036/037 show Compress-Archive selecting a staging directory. MITRE's current page includes this cmdlet in a procedure example. | No resulting ZIP was recovered, and a literal success echo is not verification. Supported as an attempted action, not proven completed archive. |

**Rejected candidate:** [T1053.005 Scheduled Task](https://attack.mitre.org/techniques/T1053/005/) initially looks plausible because the EV-017 interface labels schtasks as a scheduled-task technique. The actual available command is `/query /v /fo csv`, not task creation or task-based execution. Evidence of a created/modified task or a scheduled execution relationship would be needed before assigning that persistence/execution behavior.

The assignment does not require a Navigator layer. Do not add techniques just to fill stages or because APT29 has used them elsewhere.

## Defensive-decision worksheet — complete twice

| Field | Fill with an actual decision |
|---|---|
| Situation and information available then | Not what was learned only afterward. |
| Decision and objective | What was done or deliberately not done, and why. |
| Evidence | EV number and the specific observation available at that time. |
| Result | What was observed afterward; unknown if unmeasured. |
| Operational effect | Stopped, delayed, contained, exposed, redirected, or no demonstrated material effect. |
| Tradeoff / risk | Visibility, service impact, premature action, or allowing activity while collecting evidence. |
| Alternative available then | A realistic option within authorization, not a hindsight-only ideal. |
| Professional judgment | Explain defensibility from the information available at the time. |

Possible investigation decisions documented here include prioritizing the reported workstation and moving away from a reportedly malfunctioning tool. Do not automatically describe those as contemporaneous attack disruption. Confirm when they occurred and who made them.

## Control and recommendation worksheets

Control: **adversary action → selected control → observed effect → remaining risk**. Continued Sysmon visibility can support an exposure/detection assessment, not proof of prevention. The documented POSTs prevent an unsupported claim that all egress was blocked.

| Priority | Observed problem | Proposed future action | Expected effect | How to validate |
|---|---|---|---|---|
| Choose 1 | Specific evidence gap or failure | A scoped change to propose, not perform now | Measurable improvement | Authorized replay/test and expected telemetry. |
| Choose 2 | A different evidence-backed issue | Avoid generic “improve monitoring” | Explain the operational benefit | State success/failure criteria. |

## Evidence and formatting checklist

- [ ] Select approximately **6–8** meaningful artifacts; number/caption/reference every figure and explain what it establishes and does not establish.
- [ ] Keep long raw material in an appendix only where useful; the gallery is an archive, not the report body.
- [ ] Include a title page using the instructor's Sticky Section template, full name, date, program and cohort.
- [ ] Copy each assignment question in full before its answer; begin each major part on a new page.
- [ ] Use formal third-person technical writing, except permitted personal contribution/reflection or AI disclosure.
- [ ] Use the required one-inch margins, 11–12 point Times New Roman or Arial, single spacing and full-block paragraphs.
- [ ] Use IEEE citation style, current authoritative sources and a References section.
- [ ] Appendix A: add the actual participation/completion screen if the range supplies one. **No such screen is present in this package.** Scores are not the assignment grade.
- [ ] Appendix B: complete AI Transparency and Evidence Validation Index below.
- [ ] Submit the required single PDF, named `Gruba_Noah_CYBR641_Lab6.pdf` for Noah (other students substitute their own names).

## AI transparency — starting validation record, not a blanket endorsement

Tool: ChatGPT/Codex. Exact model/version was not independently recorded for this collection; verify it before submission. Context included lab screenshots, pasted logs and assignment/session text. Some supplied originals contained lab credentials and are excluded from the public package. Do not describe all context as sanitized if it was not.

| Assistance | Independent validation / evidence | Error or limitation | Disposition |
|---|---|---|---|
| Organize the local sequence | Compare GUIDs across EV-031/032, EV-028 and EV-018. | DNS alone cannot prove delivery. | Keep observed chain; qualify source hypothesis. |
| Suggest scheduled-task mapping | Read actual /query command in EV-037; compare current MITRE definition. | Automated UI label and initial hypothesis implied persistence. | Reject unsupported scheduled-task persistence mapping. |
| Guide packet retrieval | Expanded job bounds EV-045 and corrected bounds EV-046. | First job excluded event hours; corrected empty result user-reported; tool reportedly faulty. | Correct filter, reject absence-of-traffic inference, suspend tool branch. |
| Interpret proxy byte counts | EV-049 active format plus official Squid reference; arithmetic agrees with EV-042. | Counts include overhead; historical loaded config not independently proved. | Accept request/reply direction; reject exact-file-size claim. |
| Draft summaries and captions | Check each statement against its EV source and retain contrary explanations. | Prose can overstate actor, escalation, scope or success. | Student reviews/modifies; AI output is not evidence. |

## Authoritative technical references

Links were checked October 17, 2026. Add numbered IEEE references with access dates in the individual report rather than citing the AI-generated guide as proof of an event.

1. MITRE ATT&CK technique pages linked in the mapping table and rejected candidate above.
2. [Microsoft Sysmon documentation](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) — process/file/DNS telemetry definitions.
3. [Squid logformat reference](https://www.squid-cache.org/Doc/config/logformat/) — request/reply counters.
4. [Security Onion PCAP documentation](https://docs.securityonion.net/en/2.4/pcap.html) — retained packet retrieval and troubleshooting context, not proof the range tool worked.
