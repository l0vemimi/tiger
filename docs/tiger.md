# tiger

- [tiger](#tiger)
- [TTP](#ttp)
  - [diamond model](#diamond-model)
  - [cyber kill chain](#cyber-kill-chain)
  - [ATT\&CK](#attck)
  - [LOLBAS](#lolbas)
  - [malware](#malware)
  - [attacks](#attacks)
  - [honeypots](#honeypots)
  - [secure vs unsecure protocols](#secure-vs-unsecure-protocols)
  - [incedent response process](#incedent-response-process)
  - [threat classifications](#threat-classifications)
  - [common standards](#common-standards)
  - [tools: incident response and discovery](#tools-incident-response-and-discovery)
  - [tools for unintended purposes](#tools-for-unintended-purposes)
  - [logs](#logs)
- [programming](#programming)

---

# TTP

**tactics, techniques & procedures** is a concept to identify individual patterns of behaviour of a particular terrorist activity and to examine and categorise more general tactics and weapons used by a particular terrorist activity


## diamond model 

framework for analysing intrusions and mapping the relations between attacker, their tools, and the infastructure used to preform the attack; it's used to organise an structure intrusion analysis by categorising data into **four** components:

**adversary**: who did the attack?

**capability**: how did they do it?

**victim**: who was the target?

**infastructure**: what was used?

1. adversary

this is who is behind the attack; it can be broken down into two roles:

- **adversary operator**: the individual directly preforming the attack
- **adversary customer** the entity that benefits from the attack being preformed

an adversary can assume both of these roles or just one; typically a high-profile cyber attack involves multiple operation teams: one for initial access and another for developing the malware, and a third for exfiltrating data; the ransomware scene has adopted this structure where you will have an initial access broker providing a service, a ransomware gang lisencing their software and an affiliate preforming the attack

to start, track the online presence used, accounts seen e.g. email, social media and the intent of the attackl allowing to be able to corrolate attribute of the attack to an entity based on available data

2. capability

capability refers to the [TTPs](#ttp) the adversary uses to preform the attack; this can be categorised into:

- **tools**: the hacking tools, malware or exploit used in the attack
- **tradecraft**: the hacking technique used by the adversary e.g. exploiting [LOLBAS](#lolbas) or commands run on the system

when mapping capabilities to the diamond model, focus on datapoints that stand out, usually represented in choices an adversary will make e.g. specific malware configuration chosen, custom malware used, novel attack techniques, command line options

1. infastructure

the adversary will deploy their capabilities using infastructure, this is anything the attacker uses to deliver their capabilities; common types of infastructure:

- service accounts
- email address
- ip address
- domains
- c2 servers
- personas e.g. social media, phone numbers
- cloud services
- file shareing websites
- tor nodes
- compromised websites

4. victim

the recipient of the attack or "capabilities deployed across infastructure by the adversary"

the diamond model can be applied in combination with attack frameworks such as [cyber kill chain](#cyber-kill-chain) by associating each diamond model componenet ,where every data point or piece of evidence collected related to that stage can be mapped to an adversary, victim, infastructure or capability

## cyber kill chain

outline stages of an offensive attack and can be used as a counter measure framework and improve defence; there are several phrases in the model:

1. **reconnaissance**: getting information on the target and identifying vulnerabilities
2. **weaponisation**: creating remote access weapons such as viruses, worms or anything tailored to the vulnerabilities
3. **delivery**: transmitting the weapon to the target e.g. email attachments, websites, usb
4. **exploitation**: malware weapon's program code triggers, taking action on the target network to exploit the vulnerability
5. **installation**: malware weapon installs an access point e.g. a backdoor
6. **command & control**: malware weapon allows access to have persistent access to the target network and remote access
7. **actions on objectives**: action on goals and achievements are taken e.g. data exfiltration, data destruction, encryption, ransom 

defensive actions that can be taken against thes phases are:

1. **detect**: determine weather an intruder is present
2. **deny**: prevent information disclosure and unauthorised access 
3. **disrupt**: stop or change outbound traffic to the attacker
4. **degrade**: counter-attack command and control
5. **decieve**: interfere with command and control
6. **contain**: network segmentation changes

an alternative to cyber kill chain is ***FireEye***, a more linear model where the persistence of threates are emphasized, stressing that a *threat does not end after one cycle*; outlined below:

1. **reconnaissance**: the initial phase of gathering information on the target, involving: scanning for vulnerabilities, researching potential entry points, identifying potential targets within the organisation
2. **initial intrusion**: once enough information is gained, attempting to breach the system, which can involve: exploiting software vulnerabilities, systems, social engineering or other methods to gain initial access
3. **establishing a backdoor**: after initial access, creating a backdoor or persistent entry point into the compromised system; ensuring there is still access even if the initial breach is discovered
4. **obtain user credentials**: stealing user credentials which can involve: keylogging, phishing or exploiting weak authentication methods
5. **install various utilities**: installing various tools, utilities or malware on the compromised system to facilitate further movement, data collection, or control; these tools can include **RATs** - *remote access trojans*, **keyloggers and other types of malicious software
6. **privelage escalation / lateral movement / data exfiltration**: once inside the system, privelage escalation is done to gain more control over the network, moving laterally within the network and trying to access more valuable systems or sensitive data; data exfiltration involves stealing and transmitting valuable information out of the network
7. **maintain persistence**: this stage emphasizes the goal to maintain long-term presence within the compromised environment; by continuously evading detection, updating tools and adapting to any security measures put in place

another alternative to cyber kill chain is ATT&CK below

## ATT&CK

**adversarial tactics, techniques & common knowledge**:

is a common guideline for classifying and describing cyberattacks and intrusions; rather looking at the results of an attack or ***IoC*** - *indicator of compromise*, it identifies tactics that indicate an attack is in progress

the framework consists of 14 tactics categories consisting of "technical objectives" of an adversary, these subcategories are then further broken down into specific techniques and sub-techniques; [MITRE ATT&CK matrix](https://attack.mitre.org/#) lists all categories, subcategories and tecnhiques in detail

**resource development**: 

identifying and aquiring resources for the attack

- aquire access
- aquire infastructure
  - domains 
  - DNS server
  - virtual private server
  - server
  - botnet
  - web services
  - serverless
  - malvertising
- compromising accounts
  - social media accounts
  - email accounts
  - cloud accounts
- compromise infastructure
  - domains
  - DNS server
  - virtual private server
  - server
  - botnet
  - web services
  - serverless
  - network devices
- develop capabilities
  - malware
  - code signing certificates
  - digital certificates
  - exploits
- establish accounts
  - social media accounts
  - email accounts
  - cloud accounts
- obtain capabilities
  - malware
  - tool
  - code signing certificates
  - digital certificates
  - exploits
  - vulnerabilities
  - artificial intelligence
- stage capabilities
  - upload malware
  - upload tool
  - install digital certificate
  - drive-by target
  - link target
  - SEO poisoning

**reconnaissance**: gathering information about a target

- active scanning
  - scanning IP blocks
  - vulnerability scanning
  - wordlist scanning
- gather victim host information
  - hardware
  - software
  - firmware
  - client configurations
- gather victim identity information
  - credentials
  - email addresses
  - employee names
- gather victim network information
  - domain properties
  - DNS
  - network trust dependancies
  - network topology
  - IP addresses 
  - network security appliances
- gather victim org information
  - determine physical locations
  - buisness relationships
  - identify buisness tempo  
  - identify roles
- phishing for information
  - spearphishing service
  - spearphishing attackment
  - spearphishing link
  - spearphishing voice
- search closed sources
  - threat intel vendors
  - purchase technical data
- search open technical databases
  - DNS / passive DNS
  - WHOIS
  - digital certificates
  - CDNs
  - scan databases
- search open websites / domains    
  - social media 
  - search engines
  - code repositories
- search victim owned websites

**privelage escalation**: obtaining elavated privelages within a system or network

- abuse control mechanism
  - setuid and setgid
  - bypass user account control
  - sudo and sudo caching
  - elevated execution with prompt
  - tempoary elevated cloud access
  - TCC manipulation
- access token manipulation
  - token impersonation / theft
  - create process with token
  - make and impersonate token
  - parent PID spoofing
  - SID-history injection
- account manipulation
  - additional cloud credentials
  - additional email delegate permissions
  - additional cloud roles
  - SSH authorised keys
  - device registration
  - additional container cluster roles
  - additional local or domain groups
- boot or logon autostart execution
  - registry run keys / startup folder
  - authentication package
  - time providers
  - winlog helper DLL
  - security support provider
  - kernel modules and extensions
  - re-opened applications
  - LSASS driver
  - shortcut modification
  - port monitors
  - print processors
  - XDG autostart entries
  - active setup
  - login items
- boot or logon initialisation scripts
  - logon script (windows)
  - login hook
  - network logon script
  - RC script
  - startup items
- create or modify system process
  - launch agent 
  - systemd service
  - windows service
  - launch daemon
  - container service
- domain or tenant policy modification
  - group policy modification
  - trust modification
- escape to host
- event triggered execution
  - change default file association
  - screensaver
  - windows management instrumentation event subscription
  - unix shell configuration modification
  - trap
  - LC_LOAD_DYLIB addition
  - netsh helper DLL
  - accessability features
  - AppCert DLLs
  - AppInit DLLs
  - application shimming
  - image file execution options injection
  - powershell profile
  - emond
  - component object model hijacking
  - installer packages
  - udev rules
- exploitation for privelage escalation
- hijack execution flow
  - DLL search order hijacking
  - DLL side-loading
  - dylib hijacking
  - executable instller file permission weakness
  - dynamic linker hijackin
  - path interception by PATH environment variable
  - path interception by search order hijacking
  - path interception by unquoted path
  - service file permission weakness
  - services registry permissions weakness
  - COR_PROFILER
  - KernelCallbackTable
  - AppDomainManager
- process injection
  - dynamic-link libary injection
  - portable executable injection
  - thread execution hijacking
  - asynchronous procedure call
  - thread local storage
  - ptrace system calls
  - proc memory
  - extra window memory injection
  - process hollowing
  - process doppelganging
  - VDSO hijacking
  - ListPlanting
- scheduled tasks / jobs
  - at
  - cron
  - scheduled tasks
  - systemd timers
  - container orchestration job
- valid accounts
  - default accounts 
  - domain accounts
  - local accounts
  - cloud accounts 

**persistence**: maintaining access to a system or network

- account manipulation
  -  addition cloud credentials
  -  additional email delegate permissions
  -  additional cloud roles
  -  SSH authorised keys
  -  device registration
  -  additional container cluster roles
  -  additional local or domain groups
-  BITS job
-  boot or login autostart execution
   -  registry run keys / startup folder
   -  authentication package
   -  time providers
   -  winlog helper DLL
   -  security support provider
   -  kernel modules and extensions
   -  re-opened applications
   -  LSASS driver
   -  shortcut modification
   -  port monitors
   -  print processor
   -  XDG autostart entries
   -  active setup
   -  login items
-  boot or logon initialisation scripts
   -  logon script (windows)
   -  login hook
   -  network logon script
   -  RC scripts
   -  startup items
-  browser extensions
-  compromise host software binary
-  create account 
   -  local account
   -  domain account
   -  cloud account
-  create or modify system process
   -  launch agents
   -  systemd service
   -  windows service
   -  launch daemon
   -  container service
-  event triggered execution
   -  change default file association
   -  screensaver
   -  windows management instrumentation event subscription
   -  unix shell configuration modification
   -  trap
   -  LC_LOAD_DYLIB addition
   -  netsh helper DLL
   -  accessibility features
   -  AppCert DLLs
   -  AppInit DLLs
   -  application shimming
   -  imag file execution options injection
   -  powershell profile
   -  emond
   -  component object model hijacking 
   -  installer packages
   -  udev rules
-  external remote services
-  hijack execution flow
   -  DLL search order hijacking
   -  DLL side-loading
   -  dylib hijacking
   -  executable installer file permissions weakness
   -  dynamic linker hijacking
   -  path interception by PATH environment variable
   -  path interception by search order hijacking
   -  path interception by unquoted path
   -  services file permissions weakness
   -  services registery permissions weakness
   -  COR_PROFILER
   -  KernelCallbackTable
   -  AppDomainManager
-  implant internal image
-  modify authentication process
   -  domain controller authentication
   -  password filter DLL
   -  pluggable authentication modules
   -  ntwork device authentication
   -  reversible encryption
   -  multi-factor authentication
   -  hybrid identity
   -  network provider DLL
   -  conditional access policies
-  office application startup
   -  office template macros
   -  office test
   -  outlook forms
   -  outlook home page
   -  outlook rules
   -  add-ins
-  power settings
-  pre-OS boot
   -  system firmware
   -  component firmware
   -  bootkit
   -  ROMMONkit
   -  TFTP boot
-  scheduled task / job
   -  at
   -  cron
   -  scheduled task
   -  systemd timers
   -  container orchestration
-  server software component
   -  SQL stored procedures 
   -  transport agent
   -  web shell
   -  ISS components
   -  terminal services DLL
-  traffic signaling
   -  port knocking
   -  socket filters
-  valid accounts
   -  default accounts
   -  domain accounts
   -  local accounts
   -  cloud accounts

**lateral movement**: moving laterally within a compromised nework

**initial access**: gaining access to a system or network

- content injection
- drive-by compromise
- exploit public facing application
- external remote services
- hardware additions
- phishing
  - spearphishing
  - spearphishing link
  - spearphishing via service
  - spearphishing voice
- replication through removable media
- supply chain compromise
  - compromise software dependancies and development tools
  - compromise software supply chain
  - compromise hardware supply chain
- trusted relationship
- valid accounts
  - default accounts
  - domain accounts
  - local accounts
  - cloud accounts

**impact**: taking action to achieve attackers objectives

**exfiltration**: transferring stolen data from a compromised system

**execution**: running malicious code on a system

- cloud administration command
- command and scripting interpreter 
  - powershell
  - applescript
  - windows command shell
  - unix shell
  - visual basic
  - python
  - javascript
  - network device CLI
  - cloud API
  - AutoHotKey & AutoIT
  - lua
- container adminstration command
- deploy container
- exploitation for client execution
- inter process communication
  - component opject model
  - dynamic data exchange
  - XPC services
- native API
- scheduled task / job
  - at
  - cron
  - scheduled task
  - systemd timers
  - container orchestration job
- serverless execution
- shared modules
- software deployment tools
- system services
  - launchctl
  - service executioin
- user execution
  - malicious link
  - malicious file
  - malicious image
- windows management and instrumentation

**discovery**: identifying additional systems or information within a network

**defence evasion**: disabling or evading security measures

- abuse elevation control mechanism
  - setuid and setgid
  - bypass user account control
  - sudo and sudo caching
  - elevated execution with prompt
  - tempoary elevated cloud access
  - TCC manipulation
- access token manipulation
  - token impersonation / theft
  - create process with token
  - make and impersonate token
  - parent PID spoofing
  - SID-history injection
- BITS job
- build image on host
- debugger evasion
- deobfuscate / decode fles or information
- deploy cnotainer
- direct volume access
- domaini or tenant policy modification
  - group policy modification
  - trust modification
- execution guardrails
  - environmental keyring
  - mutual exclusion
- exploitation for defence evasion
- file directory permissions modification
  - windows file and directory permissions modification
  - linux and mac file and directory permissions modification
- hide artifacts
  - hidden files and directories
  - hidden users
  - hidden windows
  - NFTFS file attributes
  - hidden file system
  - run virtual instances
  - VBA stomping
  - email hiding rules
  - resouorce forking
  - process argument spoofing
  - ignore process interrupts
  - file / path exclusions
- hijacking execution flow
DLL search order hijacking
  -  DLL side-loading
  -  dylib hijacking
  -  executable installer file permissions weakness
  -  dynamic linker hijacking
  -  path interception by PATH environment variable
  -  path interception by search order hijacking
  -  path interception by unquoted path
  -  services file permissions weakness
  -  services registery permissions weakness
  -  COR_PROFILER
  -  KernelCallbackTable
  -  AppDomainManager
-  impair defences
   -  disable or modify tools 
   -  disable windows event logging 
   -  impair command history logging 
   -  disable or modify system firewall
   -  indicator blocking
   -  diable or modify cloud firewall
   -  disable or modify clour logs
   -  safe mode boot
   -  downgrade attack
   -  spoof security alerting
   -  disable or modify linux audit system
-  impersnoation
-  indicator removal
   -  clear windows event logs
   -  clear minux or mac system logs
   -  clear command history
   -  file deletion
   -  network share connection removal
   -  timestomp
   -  clear network connection history configurations
   -  clear mailbox data
   -  clear persistence 
   -  relocate malware
-  indirect command execution
- masqerading
  -  invalid code signature
  -  right-to-left override
  -  rename system utilities
  -  masqerade task or service
  -  match legitimate name or location
  -  space after filename
  -  double file extension
  -  masquerade file type
  -  break process trees
  -  masquerade account name
-  modify authentication process
   -  domain controller authentication
   -  password filter DLL
   -  pluggable authentication modules
   -  network device authentication
   -  reversible encryption
   -  multifactor authentication
   -  hybrid identity
   -  network provider DLL
   -  conditional access policies
-  modify cloud compute infastructure
   -   create snapshot
   -   create cloud instance
   -   delete cloud instance
   -   revert cloud instance
   -   modify cloud compute configurations
-   modify cloud resource hierarchy
-   modify registery
-   modify system image
    -   patch system image
    -   downgraed sytem image
-   network boundry bridging
    -   network address translational traversal
-   obfuscated files or information
    -   binary padding
    -   software packing
    -   stenography
    -   compile after delivery
    -   indicator removal from tools 
    -   HTML smuggling
    -   dynamic API resolution 
    -   stripped payloads
    -   embedded payloads
    -   command obfuscation
    -   fireless storage
    -   LNK icon smuggling
    -   encrypted / encoded file
    -   polymorphic code
-   plit file modification
-   pre-OS boot
    -   system firmware
    -   component firmware
    -   bootkit
    -   RMMONkit
    -   TFTP boot
-   process injection
  - dynamic-link libary injection
  - portable executable injection
  - thread execution hijacking
  - asynchronous procedure call
  - thread local storage
  - ptrace system calls
  - proc memory
  - extra window memory injection
  - process hollowing
  - process doppelganging
  - VDSO hijacking
  - ListPlanting
- reflective coad loading
- rogue domain controller
- rootkit
- subvert trust controls
  - gatekeeper bypass
  - code signing
  - SIP and trust provider hijacking
  - install root certificate
  - mark-of-the-web bypass
  - code signing policy modification
- system binary proxy execution
  - compiled HTML file
  - control panel
  - CMSTP
  - InstallUtil
  - mshta
  - msiexec
  - odbcconf
  - regsrv32
  - rundll32
  - verclsid
  - mavinject
  - MMC
  - electron applications
- system script proxy execution
  - PubPrn
  - SyncAppvPublishingServer
- template injection
- traffic signaling
  - port knocking
  - socket filters
- trusted developers utilities proxy execution
  - MSBuild
  - ClickOnce
- unused / unsupported cloud regions
- use alternate authentication maaterial
  - application access token
  - pass the hash
  - pass the ticket
  - web session cookie
- valid accounts
  - default accounts
  - domain accounts
  - local accounts
  - cloud accounts
- virtualisation / sandbox evasion
  - system checks
  - user activity based checks
  - time based evasion
- weaken encryption
  - reduce key space
  - disable crypto hardware
- XSL script processing 

**credential access**: obtaining credentials to access systems or data

**command and control**: establishing communication with compromised systems

**collection**: collecting data from compromised systems

- diamond model

---

## LOLBAS

**living off the land binaries and scripts** is a method of attack of execurables, scripts and libaries that already exist on a computer, provided by the operating system or come from trusted sources; to be classified as such, they must provide functions:

- execute program code or scripts
- compile program code
- bypass user account control
- read network traffic or user activity
- side load or hijack DLLs
- process memory dumping
- read login credentials
- file operations e.g. gile downloads and uploads

LOLBAS attacks work by using legitimate binaries to carry out malicious activities, these tools are often already present on the victims computer and can be used by attackers to evade detection by security software, e.g. an attacker can use a powershell script that is already present on the system to download and execute additional malicious coude, since powershell is a legitimate tool it may not be flagged as suspicious


## malware

**malware**, short for ***malicious software***, refers to any software intentionally created to cause harm to a computer system, server, network, or user; it is a broad term that encompasses various types of harmful software created by cybercriminals for various purposes

**virus** is a type of malware that, much like a biological virus, attaches itself to a host (e.g., a file or software) and replicates when the host is executed; viruses can corrupt, delete or modify data, and slow down system performance

**worms** are self-replicating malware that spread through networks without human intervention; they exploit system vulnerabilities, consuming bandwidth and sometimes carrying a payload to infect target machines

**trojan horse** is a piece of software disguised as a legitimate program but contains harmful code; users unknowingly download and install it, giving the attacker unauthorized access to the computer or network; trojans can be used to steal data, create a backdoor, or launch additional malware attacks
 
**ransomware** is a type of malware that encrypts its victims’ files and demands a ransom, typically in the form of cryptocurrency, for the decryption key; if the victim refuses or fails to pay within a specified time, the encrypted data may be lost forever

**spyware** is a type of malware designed to collect and relay information about a user or organization without their consent it can capture keystrokes, record browsing history, and access personal data such as usernames and passwords

**adware** is advertising-supported software that automatically displays or downloads advertising materials, often in the form of pop-up ads, on a user’s computer; while not always malicious, adware can be intrusive and open the door for other malware infections

**rootkit** is a type of malware designed to hide or obscure the presence of other malicious programs on a computer system; this enables it to maintain persistent unauthorized access to the system and can make it difficult for users or security software to detect and remove infected files

**keyloggers** are a type of malware that monitor and record users’ keystrokes, allowing attackers to capture sensitive information, such as login credentials or financial information entered on a keyboard

## attacks

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

common attacks 

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

## honeypots

decoy systems or networks designed to attract and detect unauthorized access attempts by cybercriminals,these intentionally vulnerable resources mimic legitimate targets, allowing security professionals to study attack techniques, gather threat intelligence, and divert attackers from actual critical systems; honeypots can range from low-interaction systems that simulate basic services to high-interaction ones that replicate entire network environments

they serve multiple purposes in cybersecurity: early warning systems for detecting new attack vectors, research tools for understanding attacker behavior, and diversions to waste hackers’ time and resources

deploying honeypots requires careful consideration, as they can potentially introduce risks if not properly isolated from production environments; advanced honeypots may incorporate machine learning to adapt to evolving threats and provide more convincing decoys; while honeypots are powerful tools for proactive defense, they should be part of a comprehensive security strategy rather than a standalone solution


## secure vs unsecure protocols

- ftp vs sftp 
- ssl vs tls
- ipsec
- dnssec
- ldaps
- srtp
- s/smime

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

---


# programming 

- python
- go
- javascript
- c++
- bash
- powershell 

