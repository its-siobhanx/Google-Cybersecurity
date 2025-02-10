# Types of attacks

## Common Types of Social Engineering to Watch Out For

Social engineering attacks manipulate individuals into compromising their security. Below are some common types of social engineering to be aware of:

### 1. Baiting
Baiting is a social engineering tactic that tempts people into compromising their security. A common example is **USB baiting**, where an attacker leaves an infected USB drive in a public place, hoping someone will find it and plug it into their device, thereby installing malware.

### 2. Phishing
Phishing is the use of digital communications, often in the form of emails, to trick people into revealing sensitive data or deploying malicious software. It is one of the most common forms of social engineering. Attackers typically pose as trusted entities like banks, online stores, or tech support to convince victims to click on malicious links or attachments.

### 3. Quid Pro Quo
Quid pro quo is a type of baiting used to trick someone into believing they’ll be rewarded in return for sharing access, information, or money. For example, an attacker might impersonate a loan officer at a bank and call customers, offering them a lower interest rate on their credit card. They will ask the customers to provide their account details in exchange for the "deal."

### 4. Tailgating
Tailgating, also known as **piggybacking**, is a social engineering tactic in which unauthorized individuals follow an authorized person into a restricted area. Attackers often exploit trust by closely following behind someone who has legitimate access to a secure location, bypassing physical security measures.

### 5. Watering Hole
A watering hole attack occurs when a threat actor compromises a website that is frequently visited by a specific group of users. These sites are often infected with malicious software, which can infect users when they visit. An example of this is the **Holy Water attack (2020)**, where malicious code was deployed on various religious, charity, and volunteer websites, targeting users from specific organizations.

## Types of phishing

### 1. Email Phishing
Email phishing is a type of attack where threat actors send messages pretending to be a trusted person or entity. The goal is to deceive the target into revealing sensitive information, clicking on malicious links, or downloading harmful attachments.

### 2. Smishing
Smishing is a form of phishing that uses **Short Message Service (SMS)**, the technology behind text messaging. Smishing attacks cover all text messaging platforms, including **Apple’s iMessages**, **WhatsApp**, and other mobile chat services. Attackers use these channels to trick individuals into divulging personal details or clicking on malicious links.

### 3. Vishing
Vishing refers to phishing attacks that involve **voice calls** or **voice messages** to deceive targets into providing personal information over the phone. Attackers may impersonate legitimate entities such as banks, tech support, or government agencies to create a sense of urgency or authority.

### 4. Spear Phishing
Spear phishing is a subset of email phishing in which specific individuals or organizations are targeted. This type of phishing attack is often highly personalized, with attackers focusing on key people (such as an accountant or executive) within an organization. These attacks typically involve detailed knowledge about the target to increase credibility and likelihood of success.

### 5. Whaling
Whaling is a specific type of spear phishing aimed at **high-ranking executives** or other important individuals within an organization. The goal is to steal sensitive information, access financial accounts, or execute fraudulent transactions. Whaling attacks are often more sophisticated and targeted than regular phishing attempts.

## Types of Malware

### Virus
A virus is malicious code that interferes with computer operations and damages data or software. It requires the user to install it, often via phishing campaigns with malicious links or attachments.

### Worm
A worm is malware that replicates and spreads itself across systems without user intervention. It often spreads via email or networked devices. An example is the Blaster worm, which infected Windows XP and 2000 systems.
**Note**: Worms were more common in the early 2000s but are less frequently used today.

### Trojan
A trojan, or Trojan horse, is malware disguised as a legitimate file or program. It is often delivered through seemingly harmless file downloads, allowing attackers to spy, gain access, or cause other harm.

### Adware
Adware displays advertisements within applications and is often bundled with legitimate software. However, malicious adware, a potentially unwanted application (PUA), can cause device slowdowns or install additional malware, often hidden in freeware.

### Spyware
Spyware collects and sells information without consent, often bundled with other software. It is a PUA and poses a significant risk in open-source software development, where misuse can occur.

### Scareware
Scareware uses fear tactics, such as fake warnings, to trick users into downloading malware. It spreads through emails or pop-ups, claiming that the user's data or device is at risk.

### Fileless Malware
Fileless malware infects a computer without being installed. It resides in memory and avoids touching the hard drive, making it harder to detect. Memory analysis is required for detection.

### Rootkits
Rootkits provide remote administrative access to systems, often to install additional malware or carry out attacks. They are typically spread using a dropper or loader, which installs and hides malicious code on the target system.

### Botnet
A botnet is a network of infected computers controlled by a bot-herder. The devices, infected by viruses, worms, or trojans, execute commands on behalf of the attacker, growing the network by infecting more devices.

### Ransomware
Ransomware encrypts a victim's data and demands payment for its restoration. An example is the WannaCry attack, which encrypted files until the victim paid a ransom in cryptocurrency.

## SQL Injection Categories

There are three main categories of SQL injection:

### 1. In-band SQL Injection
In-band (classic) SQL injection is the most common type, where the same communication channel is used to launch the attack and retrieve results. For example, an attacker enters a malicious query in a vulnerable search box, which then returns sensitive data like user passwords.

### 2. Out-of-band SQL Injection
Out-of-band SQL injection uses a different communication channel to launch the attack and gather results. For instance, an attacker may use a query to connect a vulnerable website to a database they control, bypassing security and stealing sensitive data. This type is rare and requires specific features on the server.

### 3. Inferential SQL Injection
Inferential SQL injection occurs when an attacker can’t directly see the results of their attack. Instead, they analyze system behavior (like error messages) to infer database structure. This allows them to craft further attacks to gain access or control over the system.

## Injection Prevention
To prevent SQL injection, user inputs must be escaped to avoid malicious code insertion. Techniques include:

- **Prepared Statements**: Execute SQL statements before passing them to a database.
- **Input Sanitization**: Remove user input that could be interpreted as code.
- **Input Validation**: Ensure user input matches system expectations.

# Threat Modeling

Threat modeling is the process of identifying assets, their vulnerabilities, and how each is exposed to threats. It is a strategic approach that combines various security activities, such as vulnerability management, threat analysis, and incident response. Security teams commonly perform these exercises to ensure their systems are adequately protected. Another key purpose of threat modeling is to proactively find ways of reducing risks to any system or business process.

## Threat Modeling Frameworks

### STRIDE
STRIDE is a threat-modeling framework developed by Microsoft. It identifies vulnerabilities in six specific attack vectors. The acronym stands for:

- **S**poofing
- **T**ampering
- **R**epudiation
- **I**nformation Disclosure
- **D**enial of Service
- **E**levation of Privilege

### PASTA
The **Process of Attack Simulation and Threat Analysis (PASTA)** is a risk-centric threat modeling process developed by OWASP leaders and supported by the cybersecurity firm VerSprite. Its focus is on discovering evidence of viable threats and representing this information as a model. PASTA’s evidence-based design is particularly useful when threat modeling applications or their supporting environments. It follows a seven-stage process that incorporates various relevant security artifacts, such as vulnerability assessments.

### Trike
Trike is an open-source methodology and tool that emphasizes a security-centric approach to threat modeling. It focuses on elements like security permissions, application use cases, privilege models, and other aspects that support a secure environment.

### VAST
The **Visual, Agile, and Simple Threat (VAST)** Modeling framework is part of an automated threat-modeling platform called ThreatModeler®. Security teams often use VAST to automate and streamline their threat modeling assessments.

