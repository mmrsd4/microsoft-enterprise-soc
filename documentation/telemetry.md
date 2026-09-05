\# Endpoint Telemetry



\## Sysmon



Sysmon is deployed on WIN-SOC01 to provide detailed endpoint

telemetry for process, network, DNS, file and process-access activity.



\## Configuration



Sysmon configuration:



\* Process creation

\* Process termination

\* Network connections

\* Process access

\* File creation

\* DNS queries



\## Event Sources



| Event ID | Event              | SOC Use                      |

| -------- | ------------------ | ---------------------------- |

| 1        | Process Create     | Process investigation        |

| 3        | Network Connection | Network investigation        |

| 5        | Process Terminate  | Process lifecycle            |

| 10       | Process Access     | Process access investigation |

| 11       | File Create        | File activity                |

| 22       | DNS Query          | DNS investigation            |



\## Validation



Telemetry was validated by generating controlled endpoint activity

and reviewing the resulting Sysmon events.



\## Limitations



This is a laboratory Sysmon configuration. Filtering and event

volume will be reviewed before forwarding telemetry to Microsoft

Sentinel.


## Microsoft Defender Telemetry

Microsoft Defender Antivirus was validated on WIN-SOC01 as the endpoint protection layer.

The endpoint generated Defender Operational events covering:

| Event ID | Activity             | SOC Use                      |
| -------- | -------------------- | ---------------------------- |
| 1000     | Scan started         | Scan activity                |
| 1001     | Scan completed       | Scan status                  |
| 1002     | Scan stopped         | Investigate incomplete scans |
| 1150     | Defender health      | Endpoint health              |
| 1151     | Health report        | Endpoint status              |
| 2000     | Intelligence update  | Protection currency          |
| 5007     | Configuration change | Configuration investigation  |

Defender status was confirmed using PowerShell.

Defender for Endpoint onboarding was not successfully verified during this phase because the Defender portal was unavailable. The Sense service and executable were present, but no SENSE operational events were generated.


## Microsoft Defender Antivirus



Microsoft Defender Antivirus is enabled on WIN-SOC01 and provides

the endpoint protection layer for the Windows laboratory system.



\### Validated Configuration



The following Defender components were checked:



\* Antivirus service

\* Real-time protection

\* Behavior monitoring

\* Network Inspection System

\* IOAV protection



\### Defender for Endpoint Status



The Defender for Endpoint Sense service and executable are present

on WIN-SOC01. However, Defender for Endpoint onboarding could not

be verified because the Microsoft Defender portal was temporarily

inaccessible during implementation.



The local MDE status registry location did not contain onboarding

status information, and the SENSE operational logs contained no

events.



Therefore, the project does not claim successful Defender for

Endpoint onboarding.



\### Current Telemetry



The current validated endpoint telemetry consists of:



\* Sysmon telemetry

\* Windows Defender Antivirus telemetry

\* Windows Defender Operational events, where available



\### Limitation



Defender for Endpoint cloud onboarding remains pending and will be

validated separately when Microsoft Defender portal access is

available.



