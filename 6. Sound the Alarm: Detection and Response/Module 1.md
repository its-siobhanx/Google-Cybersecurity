# Incident Response

## NIST Incident Response Lifecycle:
* Preparation
* Detection & Analysis
* Containment, Eradication, & Recovery
* Post-incident activity

## Roles in Incident Response

### Command, control, and communication
A Computer Security Incident Response Team (CSIRT) is a group of trained security professionals who handle incident management. For effective incident response, clear command, control, and communication are essential. Command involves strong leadership, control ensures proper management of technical aspects and resources, and communication keeps stakeholders informed. A well-defined CSIRT structure with clear roles is key to an efficient and successful response.

These professionals can be from external departments, such as human resources, public relations, management, IT, legal, and others. Security professionals involved in a CSIRT typically include three key security related roles: 
* Security analyst: Monitor the environment for security threats, which involves analyzing and triaging alerts, investigating root causes, and escalating or resolving issues. If a critical threat is detected, the analyst escalates it to the appropriate team lead, such as the technical lead.
* Technical lead: The technical lead manages the technical aspects of incident response, including applying patches and updates. They first determine the root cause of the incident, then develop strategies for containment, eradication, and recovery. They work closely with other teams to ensure the response aligns with business priorities, like minimizing customer disruptions and restoring normal operations.
* Incident coordinator: Incident response involves collaboration with non-security professionals. The incident coordinator plays a key role in coordinating with relevant departments, ensuring clear communication and keeping everyone informed about the incident's status. Incident coordinators may also be part of other teams, such as the SOC.

### SOC Secuirty Operations Center
A Security Operations Center (SOC) is responsible for monitoring networks, systems, and devices for security threats. It may function as a separate unit or within a CSIRT. The SOC is part of the blue team, which defends against security threats by engaging in activities like network monitoring, analysis, and incident response.

* Tier 1: Are the least experienced and handle tasks like monitoring, reviewing, and prioritizing alerts based on severity. They also create and close alerts using ticketing systems and escalate tickets to Tier 2 or Tier 3 when necessary.
* Tier 2: Are more experienced and handle escalated tickets from L1. They conduct deeper investigations, refine security tools, and report to the SOC Lead.
* Tier 3: Or SOC leads, are highly experienced and manage team operations. They perform advanced detection techniques like malware and forensics analysis and report to the SOC manager.
* The SOC manager: Oversees the team by hiring, training, and evaluating members. They create performance metrics, manage team performance, develop incident, compliance, and audit reports, and communicate findings to stakeholders, including executive management.

## Incident Response Tools

| Capability               | IDS | IPS | EDR |
|--------------------------|-----|-----|-----|
| Detects malicious activity| ✓   | ✓   | ✓   |
| Prevents intrusions       | N/A | ✓   | ✓   |
| Logs activity             | ✓   | ✓   | ✓   |
| Generates alerts          | ✓   | ✓   | ✓   |
| Performs behavioral analysis| N/A | N/A | ✓   |

* IDS: An Intrusion Detection System (IDS) monitors system activity to detect and alert on potential intrusions, providing continuous network event monitoring to identify security threats. However, an IDS does not prevent or stop malicious activity; it generates alerts for security professionals to investigate and respond if needed. For example, it can alert on suspicious user logins, but it won’t block the login itself. Examples of IDS tools include Zeek, Suricata, Snort®, and Sagan.
* IPS: An Intrusion Prevention System (IPS) monitors system activity for intrusions and takes action to stop them, unlike an IDS that only alerts. It detects and prevents malicious activity, such as blocking specific traffic by modifying access control lists. Many IDS tools, like Suricata, Snort, and Sagan, can also function as IPS, offering both detection and prevention capabilities.
* EDR: Endpoint Detection and Response (EDR) monitors devices (endpoints) for malicious activity. EDR tools, installed on endpoints like computers, phones, and tablets, record and analyze system activity to detect, alert, and respond to suspicious behavior. Unlike IDS/IPS, EDR tools use behavioral analysis, powered by machine learning and AI, to identify threat patterns. EDR can also automate responses to stop attacks, such as blocking unusual processes. Examples of EDR tools include Open EDR®, Bitdefender™ Endpoint Detection and Response, and FortiEDR™.

