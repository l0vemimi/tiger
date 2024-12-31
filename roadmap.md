- [fundamentals](#fundamentals)
  - [hardware](#hardware)
  - [connections](#connections)
- [operating systems](#operating-systems)
  - [os-independant troubleshooting](#os-independant-troubleshooting)
  - [windows](#windows)
  - [linux](#linux)
  - [mac](#mac)
- [network](#network)
  - [internet protocol](#internet-protocol)
  - [subnet](#subnet)
    - [pubic vs private ip address](#pubic-vs-private-ip-address)
  - [functions](#functions)
  - [network topology](#network-topology)
  - [virtualisation](#virtualisation)
  - [tools: network](#tools-network)
  - [authentication](#authentication)
- [security](#security)
  - [models and frameworks](#models-and-frameworks)
  - [malware types](#malware-types)
  - [attack types](#attack-types)
    - [common attacks](#common-attacks)
  - [zero trust](#zero-trust)
    - [backups and resiliency](#backups-and-resiliency)
  - [cyber kill chain](#cyber-kill-chain)
  - [honeypots](#honeypots)
  - [system hardening](#system-hardening)
  - [isolation](#isolation)
  - [intrusion detection \& prevention](#intrusion-detection--prevention)
  - [access control](#access-control)
    - [authentication \& authorization](#authentication--authorization)
      - [RBA](#rba)
      - [ABAC](#abac)
      - [security tokens](#security-tokens)
  - [cryptography](#cryptography)
  - [frameworks](#frameworks)
  - [understand](#understand)
  - [secure vs unsecure protocols](#secure-vs-unsecure-protocols)
  - [understand following terms](#understand-following-terms)
  - [incedent response process](#incedent-response-process)
  - [threat classifications](#threat-classifications)
  - [common standards](#common-standards)
  - [tools: incident response and discovery](#tools-incident-response-and-discovery)
  - [tools for unintended purposes](#tools-for-unintended-purposes)
  - [logs](#logs)
  - [hardening concepts](#hardening-concepts)
  - [tools: threat analysis](#tools-threat-analysis)
  - [understand audience](#understand-audience)
- [cloud skills and knowledge](#cloud-skills-and-knowledge)
  - [understand cloud services](#understand-cloud-services)
  - [cloud models](#cloud-models)
  - [common cloud environments](#common-cloud-environments)
  - [common cloud storage](#common-cloud-storage)
- [programming](#programming)


# fundamentals

## hardware

**CPU** - a ***central processing unit*** executes instructions of a computer program such as arithmetic, logic, controlling and input / output operations

**GPU** - ***graphical processing unit*** is designed for digital image processing and to accelerate computer graphics, being present either as a discrete video card or embedded on motherboards, mobile phones, personal computers, workstations, and game consoles

**RAM** - ***random access memory*** is a form of electronic computer memory that can be read and changed in any order, typically used to store working data and machine code; they allow data items to be read or written in almost the same amount of irrespective of the physical location of data inside the memory

**motherboard** - holds and allows communication between many of the crucial electronic components of a system, such as the cpu and memory, and provides connectors for other peripherals

**HDD** - ***hard disk drive***, an electro-mechanical data storage device that stores and retrieves digital data using magnetic storage with one or more rigid rapidly rotating platters coated with magnetic material; the platters are paired with magnetic heads, usually arranged on a moving actuator arm, which read and write data to the platter surface; data is accessed in a random-access manner, meaning that individual blocks of data can be stored and retrieved in any order; HDDs are a type of non-volatile storage, retaining stored data when powered off; modern HDDs are typically in the form of a small rectangular box

**SSD** - ***solid state drive***, a type of solid storage device that uses integrated circuits to store data persistently; they rely on non-volatile memory and unlike HDDs, have no moving parts, allowing them to deliver faster data access speed, reduced latency, increased resistance to physical shock, lower power consumption and silent operation

**PSU** - ***power supply unit*** converts mains AC or wall power to low-voltage regulated DC power for the internal components of a desktop

**input devices** - equipment used to provide data and control signals to an information processing system, such as a computer or information appliance, e.g. *keyboards, computer mice, scanners, cameras, joysticks,* and *microphones*

**output devices** - hardware that converts information or data into a human-perceptible form or, historically, into a physical machine-readable form for use with other non-computerized equipment; it can be text, graphics, tactile, audio, or video e.g. *monitors, printers* and *sound cards*

## connections

**bluetooth** - short-range wireless technology standard used for exchanging data between fixed and mobile devices over short distances; while it offers convenience for connecting peripherals and transferring information, it also presents several security concerns in the cybersecurity landscape; **bluetooth vulnerabilities** can potentially allow attackers to intercept communications, execute malicious code, or gain unauthorized access to devices; **common attacks include bluejacking, bluesnarfing, and bluebugging**; to mitigate these risks, cybersecurity professionals recommend regularly updating device firmware, using the latest bluetooth protocols, enabling encryption, and turning off bluetooth when not in use; despite ongoing security improvements, bluetooth remains an attack vector that requires vigilant monitoring and protection in both personal and enterprise environments

**infared** -  type of wireless communication technology that utilizes light waves in the electromagnetic spectrum to transmit data between devices; infrared connections are widely used in short-range communication, commonly found in devices like **remote controls, wireless keyboards and mice, and computer-to-printer communication**

**NFC** - ***near field communication*** is a short-range wireless technology that allows devices to communicate and exchange data over very short distances, typically up to 10 cm; NFC is commonly used for applications such as contactless payments, electronic ticketing, and data transfer between devices; it operates at a frequency of 13.56 MHz and supports various modes, including peer-to-peer communication, card emulation, and reader/writer modes; NFC enables quick and secure interactions with minimal setup, making it convenient for mobile payments, access control, and sharing information

**wifi** - a wireless networking technology that allows devices to connect to the internet and communicate with each other without physical cables; it uses radio waves to transmit data, typically operating on the 2.4 GHz and 5 GHz frequency bands; wifi networks are created by wireless routers or access points and can be found in homes, offices, public spaces, and many other locations; the technology follows IEEE 802.11 standards, with newer versions e.g. wifi 6 or 802.11ax, offering increased speeds, better performance in crowded areas, and improved energy efficiency; wifi enables the proliferation of mobile and smart devices, supporting the internet of things or *IoT* and allowing for greater flexibility and mobility in network connectivity

**IoT** - ***internet of things*** describes devices with sensors, processing ability, software and other technologies that connect and exchange data with other devices and systems over the Internet or other communication networks

**computer networking** - the practice of connecting computers and devices to share data and resources; involving use of **protocols like TCP/IP for communication, hardware such as routers and switches for directing traffic, and various network topologies** (star, mesh, bus) for organizing connections; networks can be categorized by size and scope, from **small local area networks** (***LANs***) to **wide area networks** (***WANs***) that span large geographical areas; key concepts include **IP addressing, subnetting, DNS** for name resolution, and network security measures

---

# operating systems

- installation and configuration
- different versions and differences
- navigation using gui and cli
- understanding permissions
- installing software and applications
- preform CRUD on files
- troubleshooting
- common commands

## os-independant troubleshooting

## windows

## linux

## mac

---

# network

- understand the osi model
- common protocol and uses
- common ports and uses
- ssl and tls basics
- basics of NAS and SAN

## internet protocol

## subnet

### pubic vs private ip address

- localhost
- loopback
- CIDR
- subnet mask
- default gateway

- VLAN
- DMZ
- ARP
- VM
- DHCP
- DNS
- NAT
- IP
- router
- switch
- VPN
- MAN
- LAN
- WAN
- WLAN
- NTP
- IPAM

## functions

- star
- ring
- mesh
- buns

## network topology

- SSH
- RDP
- FTP
- SFTP
- HTTP / HTTPS
- SSL /TLS

## virtualisation

- hypervisor
- guestOS
- hostOS 
- VM

## tools: network

- ipconfig
- ping
- dig
- netstat
- route
- nmap
- tcpdump
- arp
- tracert
- nslookup
- iptables

packet sniffers

port scanners

protocol analyzers

## authentication

- kerberos
- RADIUS
- LDAP
- SSO
- certificates
- local auth

---

# security

## models and frameworks

**defensive** security focuses on building and maintaining resilient systems that prevent, detect, and respond to threats primarily after an incident occurs and work on preventing attacks before they happen
**offensive** security uses a proactive approach by *seeking* vulnerabilities, flaws and weaknesses in systems before they can be exploited; this includes finding vulnerabilites in IT infastructure, applications, networks, web domains and techniques such as exploiting software flaws to access confidential data, brute forcing, DDoS attacks, social engineering

**threat intelligence**, critical components in cybersecurity that help organizations stay ahead of potential threats; **threat intell** refers to the collection, analysis, and dissemination of information about potential or current attacks targeting an organization; this intelligence typically includes details on emerging threats, attack patterns, malicious IP addresses, and indicators of compromise (IoCs), helping security teams anticipate, prevent, or mitigate cyberattacks; threat intel can be sourced from both internal data (such as logs or past incidents) and external feeds, and it helps in understanding the tactics, techniques, and procedures (TTPs) of adversaries. 

**OSINT**, a subset of threat intel, involves gathering publicly available information from open sources to assess and monitor threats; these sources include websites, social media, forums, news articles, and other publicly accessible platforms; often used for reconnaissance to identify potential attack vectors, compromised credentials, or leaks of sensitive data; also a valuable tool in tracking threat actors, as they may leave traces in forums or other public spaces

**handshake** is a process of establishing a secure connection between two parties before data exchange begins; it typically involves a series of predefined messages exchanged to verify identities, agree on communication parameters, and sometimes establish encryption keys; the most common example is the TCP three-way handshake used to initiate a connection; in cryptographic protocols like TLS/SSL, handshakes are more complex, involving certificate verification and key exchange; handshakes are crucial for ensuring secure, authenticated communications, preventing unauthorized access, and setting up the parameters for efficient data transfer in various network protocols and security systems

**CIA triad** is a fundamental model that defines three key principles: **confidentiality, integrity, and availability**; **confidentiality** ensures that data is accessible only to authorized parties; **integrity** guarantees that information remains accurate and unaltered throughout its lifecycle; **availability** ensures that data and resources are accessible to authorized users when needed, this model serves as a guide for developing security policies, designing secure systems, and evaluating the effectiveness of security measures

**privilege escalation** is a technique where an attacker increases their access level within a system, moving from lower to higher permissions, such as from a standard user to an administrator; this can be achieved by exploiting system vulnerabilities, misconfigurations, or security weaknesses; it is critical to implement ***strong access controls, adhere to the principle of least privilege, and regularly update and patch systems*** to defend against such attacks

**OWASP** ***Open Web Application Security Project*** [top 10](https://owasp.org/www-project-developer-guide/draft/training_education/owasp_top_ten/) is a regularly updated list of the most critical web application security risks and serves as a standard awareness document for developers and security professionals, highlighting the most important security concerns in web applications; the list includes **vulnerabilities** like **injection flaws, broken authentication, sensitive data exposure, XML external entities (XXE), broken access control, security misconfigurations, cross-site scripting (XSS), insecure deserialization, using components with known vulnerabilities, and insufficient logging and monitoring**

## malware types

**malware**, short for ***malicious software***, refers to any software intentionally created to cause harm to a computer system, server, network, or user; it is a broad term that encompasses various types of harmful software created by cybercriminals for various purposes

**virus** is a type of malware that, much like a biological virus, attaches itself to a host (e.g., a file or software) and replicates when the host is executed; viruses can corrupt, delete or modify data, and slow down system performance

**worms** are self-replicating malware that spread through networks without human intervention; they exploit system vulnerabilities, consuming bandwidth and sometimes carrying a payload to infect target machines

**trojan horse** is a piece of software disguised as a legitimate program but contains harmful code; users unknowingly download and install it, giving the attacker unauthorized access to the computer or network; trojans can be used to steal data, create a backdoor, or launch additional malware attacks
 
**ransomware** is a type of malware that encrypts its victims’ files and demands a ransom, typically in the form of cryptocurrency, for the decryption key; if the victim refuses or fails to pay within a specified time, the encrypted data may be lost forever

**spyware** is a type of malware designed to collect and relay information about a user or organization without their consent it can capture keystrokes, record browsing history, and access personal data such as usernames and passwords

**adware** is advertising-supported software that automatically displays or downloads advertising materials, often in the form of pop-up ads, on a user’s computer; while not always malicious, adware can be intrusive and open the door for other malware infections

**rootkit** is a type of malware designed to hide or obscure the presence of other malicious programs on a computer system; this enables it to maintain persistent unauthorized access to the system and can make it difficult for users or security software to detect and remove infected files

**keyloggers** are a type of malware that monitor and record users’ keystrokes, allowing attackers to capture sensitive information, such as login credentials or financial information entered on a keyboard

## attack types

- phishing
- wishing
- whaling
- smishing
- spam vs spim
- shoulder surfing 
- tailgating
- dumpster diving
- zero day
- social engineering
- reconnaissance 
- impersonation
- watering hole attack
- drive by attack
- typo squatting
- brute force vs password spray

### common attacks 

- dos vs ddos
- MITM
- CSRF
- spoofing
- sql injection
- xxs
- evil twin
- vlan hopping
- dns poisoning
- deauth attack
- replay attack
- rogue access point
- buffer overflow
- memory leak
- pass the hash
- directory traversal

- common hacking tools
- common exploit frameworks
- concept of defence in depth
- concept of runbooks
- basics of frensics
- concepts of threat hunting
- vulnerability management
- reverse engineering
- pen testing rules and engagement
- perimiter vs DMZ vs segmentation

## zero trust

zero trust revolve around the principle of “***never trust, always verify***,” emphasizing the need to continuously validate every user, device, and application attempting to access resources, regardless of their location within or outside the network perimeter; unlike traditional security models that rely on a strong perimeter defense, zero trust assumes that threats could already exist inside the network and that no ***entity should be trusted by default***

key principles include **strict identity verification, least privilege access, micro-segmentation, and continuous monitoring**; this approach limits access to resources based on user roles, enforces granular security policies, and continuously monitors for abnormal behavior, ensuring that security is maintained even if one segment of the network is compromised

**risk** - the possibility of damage, loss, or any negative occurrence that is caused by external or internal vulnerabilities, that may be avoided through preemptive action; risk is typically characterized by three main components:

**threat** - potential danger to the confidentiality, integrity, or availability of information in your system; threats can be natural e.g., floods, earthquakes, human-made e.g., hackers, malicious software, or due to technical issues e.g., hardware malfunction

**vulnerability** - weakness or flaw in your system that can be exploited by a threat agent to compromise the security of the system; vulnerabilities can exist in various aspects, such as physical access, network services, or security procedures

**impact** - potential amount of damage or loss that can occur to your organization, system, or data due to the successful execution of a threat; impacts can be financial, reputational, operational, or any other negative consequence that your organization faces as a result of a security breach

### backups and resiliency

**backups** involve regularly copying data to secure storage locations, ensuring data can be recovered in case of loss, corruption, or disaster

**resiliency** refers to a system’s ability to maintain operations and recover quickly from disruptions; this includes implementing redundant systems, distributing resources across multiple locations, and designing fault-tolerant architectures

effective backup and resiliency strategies incorporate diverse backup methods (full, incremental, differential), off-site storage, regular testing of recovery procedures, and automated failover mechanisms

## cyber kill chain

framework for breaking down the stages of a cyber attack, making it easier for security professionals to identify, mitigate, and prevent threats; the model breaks down the stages of a cyber attack into seven distinct phases:

**reconnaissance** involves gathering intelligence on the target, which may include researching public databases, performing network scans, or social engineering techniques

**weaponization**, when the attacker creates a weapon – such as a malware, virus, or exploit – and packages it with a delivery mechanism that can infiltrate the target’s system

**delivery**, when the attacker selects and deploys the delivery method to transmit the weapon to the target; common methods include email attachments, malicious URLs, or infected software updates

**exploitation**, the phase where the weapon is activated, taking advantage of vulnerabilities in the target’s systems or applications to execute the attacker’s code

**installation**, once the exploit is successful, the attacker installs the malware on the victim’s system, setting the stage for further attacks or data exfiltration

**command and control** ***C2***, the attacker establishes a communication channel with the infected system, allowing them to remotely control the malware and conduct further actions

**actions on objectives**, the final phase, the attacker achieves their goal, which may involve stealing sensitive data, compromising systems, or disrupting services

## honeypots

decoy systems or networks designed to attract and detect unauthorized access attempts by cybercriminals,these intentionally vulnerable resources mimic legitimate targets, allowing security professionals to study attack techniques, gather threat intelligence, and divert attackers from actual critical systems; honeypots can range from low-interaction systems that simulate basic services to high-interaction ones that replicate entire network environments

they serve multiple purposes in cybersecurity: early warning systems for detecting new attack vectors, research tools for understanding attacker behavior, and diversions to waste hackers’ time and resources

deploying honeypots requires careful consideration, as they can potentially introduce risks if not properly isolated from production environments; advanced honeypots may incorporate machine learning to adapt to evolving threats and provide more convincing decoys; while honeypots are powerful tools for proactive defense, they should be part of a comprehensive security strategy rather than a standalone solution

## system hardening

configuring and securing an OS to reduce vulnerabilities and improve its defense against attacks; this process includes disabling unnecessary services and ports, applying security patches and updates, configuring strong authentication mechanisms, enforcing least privilege principles, and enabling firewalls and intrusion detection systems; hardening also involves setting up proper file permissions, securing system logs, and regularly auditing the system to ensure compliance with security policies and best practices; the goal is to minimize the attack surface and protect the OS from potential threats and exploits

## isolation

separating systems, processes, or data to contain potential threats and minimize the impact of security breaches; involves creating boundaries between different components of a system or network to prevent unauthorized access or the spread of malware

common isolation techniques include virtual machines, containers, network segmentation, and sandboxing; isolation enhances security by limiting the attack surface, containing potential breaches, and protecting sensitive data or critical systems from compromised areas

## intrusion detection & prevention

**IDS** ***intrusion detection systems*** is a critical security tool designed to monitor and analyze network traffic or host activities for any signs of malicious activity, policy violations, or unauthorized access attempts; once a threat or anomaly is identified, the IDS raises an alert to the security administrator for further investigation and possible actions

**IPS** ***intrusion prevention systems*** is an advanced security solution closely related to IDS; while an IDS mainly focuses on detecting and alerting about intrusions, an IPS takes it a step further and actively works to prevent the attacks; it monitors, analyzes, and takes pre-configured automatic actions based on suspicious activities, such as blocking malicious traffic, reseting connections, or dropping malicious packets

## access control

### authentication & authorization

**authentication** is the process of validating the identity of a user, device, or system; it confirms that the entity attempting to access the resource is who or what they claim to be; the most common form of authentication is the use of usernames and passwords; other methods include: 2FA, biometrics, security tokens or certificates, RBAC, ACLs, ABAC

**authorization** comes into play after the authentication process is complete; it involves granting or denying access to a resource, based on the authenticated user’s privileges; authorization determines what actions the authenticated user or entity is allowed to perform within a system or application

#### RBA

**RBA** - ***role based access control*** is a policy-neutral access control mechanism defined around roles and privileges; the components of RBAC such as role-permissions, user-role and role-role relationships make it simple to perform user assignments
three primary rules are defined for RBAC:
**1. role assignment**: a subject can exercise a permission only if the subject has selected or been assigned a role;
**2. role authorization**: a subject's active role must be authorized for the subject. With rule 1 above, this rule ensures that users can take on only roles for which they are authorized;
**3. permission authorization**: a subject can exercise a permission only if the permission is authorized for the subject's active role. With rules 1 and 2, this rule ensures that users can exercise only permissions for which they are authorized

#### ABAC

**ABAC** - ***attribute based access control***, an access control paradigm whereby a subject's authorization to perform a set of operations is determined by evaluating attributes associated with the subject, object, requested operations, and, in some cases, environment attributes

#### security tokens

only the person who physically holds the token or has access to the software can produce the required code for authentication; these tokens often use time-synchronization technology to generate temporary, highly secure codes that change every few seconds

**Hardware-based Tokens**: These are physical devices, like key fobs or smart cards, that generate a security code at the push of a button or upon being plugged into a computer interface.
**Software-based Tokens**: Also known as soft tokens, these are applications or software installed on a device, such as a smartphone or computer, generating a code accessible through the device.
**SMS Tokens**: These tokens involve sending the authentication code via SMS to the user’s mobile device. While popular, they are considered less secure than hardware or software tokens due to the susceptibility of SMS to interception.

## cryptography

- salting
- hashing
- key exchange
- private vs public keys
- PKI
- obfuscation

## frameworks

- diamond model
- kill chain
- ATT&CK

## understand 

- SIEM
- SOAR

## secure vs unsecure protocols

- ftp vs sftp 
- ssl vs tls
- ipsec
- dnssec
- ldaps
- srtp
- s/smime

## understand following terms

- antivirus 
- antimalware
- edr
- dlp
- firewall & nextgen firewall
- hips
- nids
- nips
- host based firewall
- sandboxing
- eap vs peap
- wps
- ac
- wpa vs wpa2 vs wpa3 vs wep

## incedent response process

- preparation 
- identification
- containment
- eradication
- recovery 
- lesson learned


## threat classifications

- zero day
- known vs unknown
- apt

## common standards 

- iso
- rmf
- nist
- cis
- csf

## tools: incident response and discovery

- dig
- nmap
- ping
- arp
- cat
- dd
- tail
- hping
- head
- grep
- nslookup
- tracert
- winhex
- autopsy
- ipconfig
- curl
- wireshark
- memdump
- FTK imager

## tools for unintended purposes

- lolbas
- gtfobins
- wacoms

## logs

- event logs
- sysogs
- netflow
- packet captures
- firewall logs

## hardening concepts

- mac based
- nac based
- port blocking
- group policy
- sinkholes
- acls
- patching
- jump server
- endpoint security

## tools: threat analysis

- virus total 
- urlscan
- anyrun
- joe sandbox
- urlvoid
- whois

## understand audience

- stakehlders
- hr
- legal 
- compliance
- management


---

# cloud skills and knowledge

- concept of security in the cloud
- difference between cloud and on-premises
- concept of infastracture as code
- concept of serverless
- basics and general flow of deploying in the cloud 

## understand cloud services

- SaaS
- PaaS
- IaaS

## cloud models

- private
- public 
- hybrid

## common cloud environments

- aws 
- gcp
- azure

## common cloud storage

- s3 
- dropbox
- icloud
- box
- onedrive
- google drive

---

# programming 

- python
- go
- javascript
- c++
- bash
- powershell 

