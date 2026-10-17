# 5. Understand recovery limits and tool problems

[Gallery](README.md) · [Noah / Start here](../README.md) · [Findings](../FINDINGS.md)

<a id="ev-038"></a>

## EV-038 — Analyst FileFinder search parameters

**Look for:** The expanded all-profile glob patterns target the distinctive staging path, archive and direct children with hashing/collection enabled.

**Do not conclude:** This is analyst collection code, not malware source; configuration alone is not a recovered artifact.

[![EV-038: Analyst FileFinder search parameters](images/EV-038_filefinder-expanded-parameters.png)](images/EV-038_filefinder-expanded-parameters.png)

[Open original image](images/EV-038_filefinder-expanded-parameters.png) · [Verify hash](manifest.csv)

---

<a id="ev-039"></a>

## EV-039 — FileFinder returned no artifacts

**Look for:** The view shows zero rows, zero uploads and zero files.

**Do not conclude:** The cropped view lacks the flow ID/completion state; absence of a recovered file is not proof of deletion or failed creation.

[![EV-039: FileFinder returned no artifacts](images/EV-039_filefinder-zero-results.png)](images/EV-039_filefinder-zero-results.png)

[Open original image](images/EV-039_filefinder-zero-results.png) · [Verify hash](manifest.csv)

---

<a id="ev-040"></a>

## EV-040 — No matching deletion events

**Look for:** The targeted staging-name Sysmon deletion-event search shows zero matches.

**Do not conclude:** This does not establish comprehensive deletion coverage, non-deletion, or whether the files ever existed.

[![EV-040: No matching deletion events](images/EV-040_staging-deletion-search-zero.png)](images/EV-040_staging-deletion-search-zero.png)

[Open original image](images/EV-040_staging-deletion-search-zero.png) · [Verify hash](manifest.csv)

---

<a id="ev-043"></a>

## EV-043 — Completed PCAP jobs

**Look for:** Jobs 1001 and 1002 display Completed on site-onion-sensor.

**Do not conclude:** Completion does not mean packets were found. Queue/completion dates are not the traffic-filter date range.

[![EV-043: Completed PCAP jobs](images/EV-043_pcap-completed-jobs.png)](images/EV-043_pcap-completed-jobs.png)

[Open original image](images/EV-043_pcap-completed-jobs.png) · [Verify hash](manifest.csv)

---

<a id="ev-044"></a>

## EV-044 — Job 1002 returned zero packets

**Look for:** The packet view shows no rows for the requested external destination.

**Do not conclude:** Its filter was later shown to exclude the uploads. This cannot test packet availability at the incident time.

[![EV-044: Job 1002 returned zero packets](images/EV-044_pcap-job-1002-zero-packets.png)](images/EV-044_pcap-job-1002-zero-packets.png)

[Open original image](images/EV-044_pcap-job-1002-zero-packets.png) · [Verify hash](manifest.csv)

---

<a id="ev-045"></a>

## EV-045 — The incorrect time filter was identified

**Look for:** Expanded job 1002 bounds run from Oct. 16 17:17 to Oct. 17 17:17 at UTC-04:00.

**Do not conclude:** That is a 24-hour interval beginning after the 13:05 uploads, not both complete calendar days.

[![EV-045: The incorrect time filter was identified](images/EV-045_pcap-job-1002-filter-details.png)](images/EV-045_pcap-job-1002-filter-details.png)

[Open original image](images/EV-045_pcap-job-1002-filter-details.png) · [Verify hash](manifest.csv)

---

<a id="ev-046"></a>

## EV-046 — Corrected PCAP job bounds

**Look for:** Job 1003 covers Oct. 16 13:00–13:10 at UTC-04:00, TCP destination 13.248.216.40:80, and shows completion.

**Do not conclude:** Its empty packet result was reported by the user, not visible in this crop. Security Onion was reportedly faulty; do not infer absent traffic.

[![EV-046: Corrected PCAP job bounds](images/EV-046_pcap-job-1003-corrected-filter.png)](images/EV-046_pcap-job-1003-corrected-filter.png)

[Open original image](images/EV-046_pcap-job-1003-corrected-filter.png) · [Verify hash](manifest.csv)

---

[Previous chapter](04-uploads-and-proxy.md) · [Next chapter](06-background-and-rejected-leads.md)
