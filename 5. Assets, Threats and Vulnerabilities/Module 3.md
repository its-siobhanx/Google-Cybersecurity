# OWASP Top 10
What is OWASP?
OWASP is a nonprofit foundation that works to improve the security of software. OWASP is an open platform that security professionals from around the world use to share information, tools, and events that are focused on securing the web.



Businesses often make critical security decisions based on the vulnerabilities listed in the [OWASP Top 10](https://owasp.org/www-project-top-ten/). This resource influences how businesses design new software that will be on their network, unlike the CVE® list, which helps them identify improvements to existing programs. Below are some of the most regularly listed vulnerabilities to be aware of:

## 1. Broken Access Control
Access controls limit what users can do in a web application. For example, a blog might allow visitors to post comments on a recent article but restrict them from deleting the article entirely. Failures in these mechanisms can lead to unauthorized information disclosure, modification, or destruction. They can also give someone unauthorized access to other business applications.

## 2. Cryptographic Failures
Information is one of the most important assets businesses need to protect. Privacy laws such as General Data Protection Regulation (GDPR) require sensitive data to be protected by effective encryption methods. Vulnerabilities can occur when businesses fail to encrypt things like personally identifiable information (PII). For example, if a web application uses a weak hashing algorithm, like MD5, it’s more at risk of suffering a data breach.

## 3. Injection
Injection occurs when malicious code is inserted into a vulnerable application. Although the app appears to work normally, it does things that it wasn’t intended to do. Injection attacks can give threat actors a backdoor into an organization’s information system. A common target is a website’s login form. When these forms are vulnerable to injection, attackers can insert malicious code that gives them access to modify or steal user credentials.

## 4. Insecure Design
Applications should be designed in such a way that makes them resilient to attack. When they aren’t, they’re much more vulnerable to threats like injection attacks or malware infections. Insecure design refers to a wide range of missing or poorly implemented security controls that should have been programmed into an application when it was being developed.

## 5. Security Misconfiguration
Misconfigurations occur when security settings aren’t properly set or maintained. Companies use a variety of different interconnected systems. Mistakes often happen when those systems aren’t properly set up or audited. A common example is when businesses deploy equipment, like a network server, using default settings. This can lead businesses to use settings that fail to address the organization's security objectives.

## 6. Vulnerable and Outdated Components
Vulnerable and outdated components is a category that mainly relates to application development. Instead of coding everything from scratch, most developers use open-source libraries to complete their projects faster and easier. This publicly available software is maintained by communities of programmers on a volunteer basis. Applications that use vulnerable components that have not been maintained are at greater risk of being exploited by threat actors.

## 7. Identification and Authentication Failures
Identification is the keyword in this vulnerability category. When applications fail to recognize who should have access and what they’re authorized to do, it can lead to serious problems. For example, a home Wi-Fi router normally uses a simple login form to keep unwanted guests off the network. If this defense fails, an attacker can invade the homeowner’s privacy.

## 8. Software and Data Integrity Failures
Software and data integrity failures are instances when updates or patches are inadequately reviewed before implementation. Attackers might exploit these weaknesses to deliver malicious software. When that occurs, there can be serious downstream effects. Third parties are likely to become infected if a single system is compromised, an event known as a supply chain attack.

**A famous example of a supply chain attack is the [SolarWinds cyber attack (2020)](https://www.cnbc.com/2020/12/13/solarwinds-hack-what-you-need-to-know-about-the-russian-cyberattack.html)**, where hackers injected malicious code into software updates that the company unknowingly released to their customers.

## 9. Security Logging and Monitoring Failures
In security, it’s important to be able to log and trace back events. Having a record of events like user login attempts is critical to finding and fixing problems. Sufficient monitoring and incident response is equally important.

## 10. Server-Side Request Forgery
Companies have public and private information stored on web servers. When you use a hyperlink or click a button on a website, a request is sent to a server that should validate who you are, fetch the appropriate data, and then return it to you. Server-side request forgeries (SSRFs) are when attackers manipulate the normal operations of a server to read or update other resources on that server. These are possible when an application on the server is vulnerable. Malicious code can be carried by the vulnerable app to the host server that will fetch unauthorized data.


Useful OSINT tools:
* [VirusTotal](https://www.virustotal.com/gui/home/upload) is a service that allows anyone to analyze suspicious files, domains, URLs, and IP addresses for malicious content.
* [MITRE ATT&CK](https://attack.mitre.org/) is a knowledge base of adversary tactics and techniques based on real-world observations.
* [OSINT Framework](https://osintframework.com/) is a web-based interface where you can find OSINT tools for almost any kind of source or platform.
* [have I been pwned](https://haveibeenpwned.com/) is a tool that can be used to search for breached email accounts.

