\# Microsoft Defender



\## Purpose



Microsoft Defender Antivirus provides endpoint protection on

WIN-SOC01.



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



\## Defender for Endpoint



The Microsoft Defender for Endpoint Sense component is present on

the endpoint.



Current state:



\* Sense executable: present

\* Sense service: stopped

\* SENSE telemetry: no events

\* MDE onboarding: not verified



The Defender portal was temporarily inaccessible during

implementation, so successful cloud onboarding is not claimed.



\## Validation



Defender configuration was validated using PowerShell.



Windows Defender Operational events and threat history were checked

to determine whether endpoint security telemetry was available.



\## Limitations



Defender for Endpoint cloud functionality depends on the available

Microsoft licensing, tenant configuration and successful endpoint

onboarding.



The project documents only functionality that was actually

validated.



