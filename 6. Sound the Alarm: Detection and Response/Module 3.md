# Incident Detection and Verification

## The Pyramid of Pain
Not all indicators of compromise are equal in the value they provide to security teams. It’s important for security professionals to understand the different types of indicators of compromise so that they can quickly and effectively detect and respond to them.
[Pyramid of Pain](https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)

1. **Hash values:** Hashes that correspond to known malicious files. These are often used to provide unique references to specific samples of malware or to files involved in an intrusion.
2. **IP addresses:** An internet protocol address like 192.168.1.1
3. **Domain names:** A web address such as www.google.com 
4. **Network artifacts:** Observable evidence created by malicious actors on a network. For example, information found in network protocols such as User-Agent strings. 
5.**Host artifacts:** Observable evidence created by malicious actors on a host. A host is any device that’s connected on a network. For example, the name of a file created by malware.
6. **Tools:** Software that’s used by a malicious actor to achieve their goal. For example, attackers can use password cracking tools like John the Ripper to perform password attacks to gain access into an account.
7. **Tactics, techniques, and procedures (TTPs):** This is the behavior of a malicious actor. Tactics refer to the high-level overview of the behavior. Techniques provide detailed descriptions of the behavior relating to the tactic. Procedures are highly detailed descriptions of the technique. TTPs are the hardest to detect.

