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

# Cloud Security Considerations

Many organizations adopt cloud services for their ease and speed of deployment, cost savings, and scalability. However, cloud computing introduces unique security challenges that cybersecurity analysts must address.

## Identity and Access Management (IAM)

IAM encompasses the processes and technologies used to manage digital identities and their access to resources. A common cloud security issue is misconfigured user roles. Improperly configured roles can grant unauthorized access to critical cloud operations, significantly increasing risk. Regularly reviewing and tightening IAM configurations is crucial.

## Configuration

The expanding cloud ecosystem adds considerable complexity to network management. Each cloud service requires precise configuration to meet security and compliance standards. This complexity is amplified during cloud migrations, where ensuring accurate configuration for every migrated process is essential. Misconfigurations are a frequent cause of breaches, making meticulous attention to detail by network administrators and architects paramount, both during migration and ongoing management.

## Attack Surface

Cloud Service Providers (CSPs) offer a wide range of applications and services, each with its own set of risks and vulnerabilities. Every new service or application increases an organization's attack surface. While a larger attack surface necessitates stronger security measures, a well-designed cloud architecture can leverage multiple services *without* necessarily increasing the number of entry points into the organization's network. It's important to remember that CSPs often employ more robust security measures than traditional on-premises networks and undergo more scrutiny.

## Zero-Day Attacks

Zero-day attacks (previously unknown exploits) are a concern for both cloud and on-premises environments. CSPs are often better positioned to detect and respond to zero-day attacks due to their scale and resources. They can patch hypervisors and migrate workloads, minimizing customer impact. Organizations should also utilize available tools for patching at the operating system level.

## Visibility and Tracking

While network administrators typically have complete visibility into on-premises network traffic, cloud environments present a different landscape. CSPs provide tools like flow logs and packet mirroring, but they do *not* allow customers to monitor traffic on the CSP's servers. This lack of full visibility can be a concern for organizations accustomed to complete control. However, CSPs undergo third-party audits to verify their security posture, which can help organizations assess their own on-premises vulnerabilities and compliance.

## Rapid Change in the Cloud

CSPs constantly update their technologies and services. This rapid pace of change can be challenging for organizations, as cloud service updates may require adjustments to security configurations and IT processes. Organizations must adapt their processes to align with CSP changes while maintaining established security best practices.

## Shared Responsibility Model

A fundamental

Key Characteristics:

*   **Passive Monitoring:**  IDS primarily observes traffic and system events without actively blocking or altering them.
*   **Signature-Based or Anomaly-Based Detection:** IDS can use signature-based detection (looking for known attack patterns) or anomaly-based detection (identifying deviations from normal behavior).

# Cryptography in the Cloud

Cryptography plays a crucial role in securing data processed and stored in cloud environments. By using encryption and secure key management systems, cryptography ensures data integrity and confidentiality.  Encryption is a cornerstone of protecting sensitive information in the cloud.

## Encryption

Encryption transforms information into ciphertext, making it unreadable without the corresponding decryption key.  Historically, encryption involved manual encoding using algorithms.  Modern encryption, however, relies on the secrecy of the *key* rather than the algorithm itself. Cryptography is an essential tool for securing cloud networks and data at rest, preventing unauthorized access.  (A more in-depth exploration of cryptography will be covered in a future course.)

## Cryptographic Erasure (Crypto-shredding)

Cryptographic erasure, also known as crypto-shredding, is a method of data destruction that focuses on erasing the encryption key rather than the data itself. Traditional data destruction methods are often less effective in cloud environments. Crypto-shredding renders data indecipherable by destroying the cryptographic keys used to encrypt it.  It's crucial that *all* copies of the key are destroyed to prevent any future access to the data.

## Key Management

The security of modern encryption hinges on keeping encryption keys secure.  Several measures can be taken to protect data when using cloud applications:

*   **Trusted Platform Module (TPM):** A TPM is a hardware chip that securely stores passwords, certificates, and encryption keys.

*   **Cloud Hardware Security Module (CloudHSM):** A CloudHSM is a dedicated computing device that provides secure storage for cryptographic keys and performs cryptographic operations like encryption and decryption.

While organizations and customers don't typically have direct access to the CSP's infrastructure, they can request audits and security reports.  Customers often don't have access to the specific encryption keys used by CSPs.  However, many CSPs offer the option for customers to provide and manage their own encryption keys, depending on the specific service.  In such cases, the customer assumes full responsibility for the confidentiality and security of these customer-managed keys.  The CSP's ability to assist in case of key compromise or loss is limited.

One advantage of the shared responsibility model is that customers aren't solely responsible for the maintenance of the cryptographic infrastructure.  Organizations can assess the risk associated with CSP-managed infrastructure by reviewing the CSP's audits and security controls.  For US federal contractors, FEDRAMP provides a list of verified CSPs.
