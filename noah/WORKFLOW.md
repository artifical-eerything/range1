# A beginner-friendly investigation workflow

[Start here](README.md) · [Meeting guide](MEETING-GUIDE.md) · [Terms](TERMS.md)

## The short version

**Ask one question → inspect a source → preserve the result → explain its limits → decide the next useful step.**

For the assignment, extend that into: **adversary action → evidence → defensive decision → result → operational effect → lesson**. A plausible attack step is not an observed one.

## 1. Establish the question and boundaries

Write a specific question, such as “What process wrote WdBoot?” rather than “Find all bad activity.” Identify the host, event date, timezone and authorized actions. The scenario is assume-breach: do not manufacture an original entry vector just to complete a story.

Noah's investigation was conducted under a user-stated detection/documentation-only boundary: no containment, remediation or victim RDP. Puppet was identified as exercise provisioning. Traffic to/from `10.10.3.0/24` was excluded. The assignment's broader Stop/Contain/Mitigate goals do not retroactively establish authorization or actions actually taken. Confirm the current instructor-approved boundary before any future live operation.

## 2. Choose the right source

| Question | Source used here | What it cannot automatically tell you |
|---|---|---|
| What program started another program? | Sysmon process events in Splunk | User intent or successful privilege escalation. |
| What program wrote a file? | Sysmon file-create event | Whether it downloaded the bytes from a particular site. |
| What name was resolved? | Sysmon DNS event | Whether a connection or file transfer followed. |
| What web request was recorded? | Proxy access log in Splunk | The uploaded content unless a body was separately retained. |
| What files are available now? | Authorized Velociraptor collection | Everything that existed previously. |
| How are byte fields defined? | Read-only local copy of proxy configuration plus documentation | Exact historical loaded state or file-only upload sizes. |

Security Onion was reported to be malfunctioning in this exercise. Its empty retrievals were not treated as absent-traffic evidence. Do not repeat a tool branch just because its results are empty.

## 3. Run one narrow, read-only check

Use the [complete search examples](SEARCHES.md) only in the authorized lab. Replace the whole Splunk search field rather than appending to an old query. Prefer original events when validating a conclusion; a table may hide important fields.

The same time can display as **13:05 UTC−04:00**, **17:05 UTC**, or **10:05 Pacific daylight time** on October 16, 2026. Record the timezone with every important timestamp. A date-only-looking selection may still preserve a time of day; verify the submitted filter.

## 4. Preserve what matters

Give a meaningful artifact a stable EV number and filename. Preserve the original; compute SHA-256 to identify that exact file; record source, collection time and limits. Event time is when the activity happened. Collection time is when the analyst saved evidence. Do not replace one with the other.

Keep passwords/private logs out of public GitHub. A private folder inside a public repository is **not** private. Private originals must remain outside the repository, not merely hidden from its README.

## 5. Build a small chain, not a pile of screenshots

For this case the strongest link is the **same process GUID** across DNS, file creation and child execution. A process name alone is weaker because multiple instances may exist. Proxy timing adds corroboration, but does not uniquely attribute a request to a process.

For every conclusion record:

| Evidence | Interpretation | Alternative | Limitation | Confidence |
|---|---|---|---|---|
| Exact field/EV ID | Best-supported explanation | A reasonable different explanation | What is not known | High / moderate / low, with a reason |

“No results” means the particular query returned none. It does not by itself mean deleted, prevented, never happened or fully scoped.

## 6. Separate execution from operational effect

A command string demonstrates a request or attempt. A child process demonstrates execution. An exit status can support completion. A verified state change or measured network effect is stronger evidence of impact.

Likewise, a Blue Team search can **expose** activity without **stopping** it. Do not claim prevention or containment merely because the team found the malware.

## 7. Stop or reopen deliberately

Close a branch when available sources do not resolve it and no distinct authorized source is available. Record the limitation. Reopen only with a new source, a corrected invalid filter, or a concrete assignment need. Do not install agents, enable logging, change permissions, restart services or execute evidence scripts to make a report look complete.

## What students do next

Use the shared evidence to support individual reasoning. Document two decisions actually made, one useful control and its limits, three conclusions with alternatives, current ATT&CK validation, and a measurable outcome. If group action evidence is missing, ask classmates for that evidence; do not fill the gap with an invented action.
