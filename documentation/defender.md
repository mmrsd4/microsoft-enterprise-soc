\# Microsoft Defender



\## Purpose



Microsoft Defender Antivirus is used as the endpoint protection layer for WIN-SOC01.



The purpose of this phase was to validate the local Defender configuration and confirm that Windows Defender Operational telemetry is available for later SOC monitoring.



\## Endpoint



| Field                | Value          |

| -------------------- | -------------- |

| Hostname             | WIN-SOC01      |

| Operating System     | Windows 10 Pro |

| Defender Antivirus   | Enabled        |

| Real-time Protection | Enabled        |

| Behavior Monitoring  | Enabled        |

| Network Inspection   | Enabled        |

| IOAV Protection      | Enabled        |

| Script Scanning      | Enabled        |



\## Validation



Defender status was checked using `Get-MpComputerStatus`.



The following protection components were confirmed as enabled:



\* Microsoft Defender Antivirus

\* Real-time protection

\* Behavior monitoring

\* Network Inspection System

\* IOAV protection

\* Script scanning



The Windows Defender Operational event log was also reviewed.



Observed event types included:



\* Event ID 1150 — Defender client health

\* Event ID 1151 — Endpoint protection health report

\* Event ID 1000 — Scan started

\* Event ID 1001 — Scan completed

\* Event ID 1002 — Scan stopped before completion

\* Event ID 2000 — Security intelligence update

\* Event ID 5007 — Defender configuration change



\## Configuration Change Investigation



Several Event ID 5007 records were observed.



The detailed event data showed changes to Defender internal configuration values, including `ToastOrSsoTrigger`, `WdConfigHash`, and internal feature-control values.



These events were not treated as malicious based only on the generic Event ID 5007 message. The actual old and new values were inspected before drawing a conclusion.



No Defender threat detections were present when `Get-MpThreatDetection` and `Get-MpThreat` were checked.



\## Defender for Endpoint Status



The Defender for Endpoint `Sense` service and `MsSense.exe` executable were present on WIN-SOC01.



However, Defender for Endpoint onboarding could not be verified during implementation because access to the Defender portal was unavailable.



The `Sense` service was stopped and the SENSE operational logs contained no events.



Therefore, Defender for Endpoint onboarding is not claimed as successfully implemented in this laboratory.



\## Limitations



This phase validates Microsoft Defender Antivirus locally.



Defender for Endpoint functionality was not confirmed because the required portal access/onboarding could not be completed during implementation.



No production Defender environment was used.



No real malware was introduced into the laboratory.



\## SOC Relevance



The Defender telemetry provides endpoint security information that can later be correlated with Sysmon and other Microsoft security telemetry.



The configuration-change investigation also demonstrates that an analyst should inspect the actual event data rather than automatically treating every Defender configuration-change event as malicious.



