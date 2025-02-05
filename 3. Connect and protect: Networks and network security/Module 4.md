## Brute Force Attacks and Prevention
A brute force attack is a trial-and-error method used to guess private information, like passwords.  Types include:
*   **Simple Brute Force:**  Trying various username/password combinations.
*   **Dictionary Attack:** Using lists of common passwords and leaked credentials.

Attackers often use tools to automate brute force attacks due to the time-consuming nature of manual attempts.

### Vulnerability Assessment
Organizations can proactively assess vulnerabilities using:
*   **Virtual Machines (VMs):** Software versions of physical computers. VMs provide an isolated environment for testing suspicious files and simulating incidents, preventing harm to the host system.  While VMs offer increased security, there's a small risk of "escape."
*   **Sandbox Environments:** Isolated testing environments for executing software or programs.  Used for testing patches, identifying bugs, evaluating suspicious software, and simulating attacks. Sandboxes can be physical or virtual.  Some malware can detect sandbox environments and behave differently.

### Prevention Measures
Common prevention measures against brute force and similar attacks:
*   **Salting and Hashing:** Hashing converts data into a one-way, unique value. Salting adds random characters to hashed passwords, increasing their complexity and security.
*   **Multi-Factor Authentication (MFA) and Two-Factor Authentication (2FA):** MFA requires multiple verification methods (e.g., password, fingerprint, OTP). 2FA uses two verification methods.
*   **CAPTCHA and reCAPTCHA:** CAPTCHAs are tests to verify users are human, preventing automated brute force attempts. reCAPTCHA is a free CAPTCHA service from Google.
*   **Password Policies:** Standardize good password practices with guidelines on password complexity, update frequency, reuse restrictions, and login attempt limits.

# Network Hardening - Firewalls, Intrusion Detection/Prevention, and SIEM

This document outlines key network security components: Firewalls, Intrusion Detection/Prevention Systems (IDS/IPS), and Security Information and Event Management (SIEM).

## Firewalls

A firewall controls network traffic by allowing or blocking packets based on a predefined set of rules.  It inspects packet headers and makes decisions based on the information they contain.  Firewalls operate at the network layer and transport layer, and can filter based on source/destination IP addresses, ports, protocols, and other header fields.  It's crucial to understand that firewalls only examine header information; they do not inspect the payload of the packets.

## Intrusion Detection System (IDS)

An Intrusion Detection System (IDS) passively monitors network traffic and/or system activity for malicious activity or policy violations.  It identifies suspicious patterns and alerts administrators to potential security incidents.

Key Characteristics:

*   **Passive Monitoring:**  IDS primarily observes traffic and system events without actively blocking or altering them.
*   **Signature-Based or Anomaly-Based Detection:** IDS can use signature-based detection (looking for known attack patterns) or anomaly-based detection (identifying deviations from normal behavior).
*   **Alert
