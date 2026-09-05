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



