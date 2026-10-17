# Session context: notes are not the same as evidence

[Start here](README.md) · [Findings](FINDINGS.md)

## Sources and purpose

Two user-supplied sources informed this study guide: a classroom-session overview and the CYBR641 Lab 6 / Session 8 assignment text. They describe an **APT29 Variant 1, assume-breach** live-fire exercise in SimSpace, followed by debrief and individual post-operation analysis. Facilitators named in the overview include Faisal, Alex and SimSpace support. Their statements and scenario labels provide context; they do not replace artifacts for technical findings.

This repository folder is a shared study/evidence collection, not an instructor-approved answer key. The complete instructor materials remain the authority for grading, scope, deadlines and permissions. The posted overview excerpt ended during the environment description; it was not a complete transcript. Full instructor text is not republished here.

## Reconcile these statements before writing

| Classroom overview statement | Evidence-based wording for this collection |
|---|---|
| WdBoot came from techiefly via Chrome. | The same network_mgr GUID performs DNS, local write and launch. The domain is a suspected source; Chrome delivery and a completed transfer are not independently shown. |
| Swipeservice beacons every ~30 seconds and is a known APT29/SolarWinds C2. | Update/registration requests are observed. Cadence and historical real-world attribution were not validated here. Describe suspected check-in behavior, not verified attribution. |
| Exfiltration used olabdatabase.com. | The actual records show **olapdatabase[.]com**, with a p. Preserve the spelling in the evidence. |
| Domain-admin credential use confirms escalation. | The credential-bearing relaunch command does not prove theft or domain-admin status; WdBoot was already SYSTEM. Sensitive originals remain private. |
| Firewall rules allowed exfiltration and were deleted. | Commands add **block** rules for outbound UDP local ports 137/53, then request deletion. They are not HTTP allow rules; effectiveness is not fully verified. |
| Only one endpoint was compromised. | Current user-directed scope and matching filename-based events are BR-WIN10-1. That is not comprehensive proof that nothing else was affected. |
| Audit policy manipulation hid activity while Sysmon stayed on. | Detailed Tracking disable/enable commands and continued Sysmon records are observed. Do not claim all Windows auditing was disabled or exact suppression duration was verified. |

## Assignment goals versus actual actions

The assignment lists **Stop Attack → Contain → Mitigate** as intended defensive outcomes. Noah's recorded investigation followed an explicit detection/documentation-only boundary: no containment, remediation or victim RDP. Those are different statements, not a reason to retroactively claim actions occurred.

At the next meeting, ask classmates for action/result artifacts if the unified Blue Team performed containment or mitigation. Until supplied, report those effects as unverified in this evidence set. Do not rank classmates or use the SimSpace score as the main analytical outcome.

## Assume-breach changes the question

The scenario starts with a foothold. This can evaluate post-compromise visibility, investigation and response. It does not independently show how a real attacker would have gained initial access or whether a perimeter/preventive control would have stopped that first compromise. A missing original download does not require endless hunting or an invented entry stage.

## For the next meeting

Use the overview to generate questions. Use original artifacts and current authoritative technical sources to support answers. Label each statement **observed**, **inferred**, **context** or **unknown**, and revise an earlier statement when the evidence contradicts it.
