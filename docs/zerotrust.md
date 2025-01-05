# zerotrust

- [zerotrust](#zerotrust)
  - [principles](#principles)
  - [CIA triad](#cia-triad)
  - [system hardening](#system-hardening)
  - [isolation](#isolation)
  - [intrusion detection \& prevention](#intrusion-detection--prevention)
  - [access control](#access-control)
    - [authentication \& authorization](#authentication--authorization)
      - [RBA](#rba)
      - [ABAC](#abac)
      - [security tokens](#security-tokens)
  - [cryptography](#cryptography)
  - [hardening concepts](#hardening-concepts)
  - [tools: threat analysis](#tools-threat-analysis)
  - [authentication](#authentication)
  - [understand](#understand)

zero trust revolve around the principle of “***never trust, always verify***,” emphasizing the need to continuously validate every user, device, and application attempting to access resources, regardless of their location within or outside the network perimeter; unlike traditional security models that rely on a strong perimeter defense, zero trust assumes that threats could already exist inside the network and that no ***entity should be trusted by default***

key principles include **strict identity verification, least privilege access, micro-segmentation, and continuous monitoring**; this approach limits access to resources based on user roles, enforces granular security policies, and continuously monitors for abnormal behavior, ensuring that security is maintained even if one segment of the network is compromised

**risk** - the possibility of damage, loss, or any negative occurrence that is caused by external or internal vulnerabilities, that may be avoided through preemptive action; risk is typically characterized by three main components:

**threat** - potential danger to the confidentiality, integrity, or availability of information in your system; threats can be natural e.g., floods, earthquakes, human-made e.g., hackers, malicious software, or due to technical issues e.g., hardware malfunction

**vulnerability** - weakness or flaw in your system that can be exploited by a threat agent to compromise the security of the system; vulnerabilities can exist in various aspects, such as physical access, network services, or security procedures

**impact** - potential amount of damage or loss that can occur to your organization, system, or data due to the successful execution of a threat; impacts can be financial, reputational, operational, or any other negative consequence that your organization faces as a result of a security breach

## principles 

**1. know your architecture, including users, devices, services and data**

in order to get the benefits from zero trust, you need to know about each component of your architecture. this will allow you to identify where your key resources are, the main risks to your architecture and also avoid any late stage pitfalls integrating legacy services which do not support zero trust.

**2. know your user, service and device identities**

an identity can represent a user (a human), service (software process) or device. each should be uniquely identifiable in a zero trust architecture. this is one of the most important factors in deciding whether someone or something should be given access to data or services.

**3. assess your user behaviour, devices and services health**

user behaviour, and service or device health, are important indicators when looking to establish confidence in the security of your systems, making them important signals for policy engines. therefore, having the ability to measure user behaviour, device and service health is key in a zero trust architecture.

**4. use policies to authorise requests**

each request for data or services should be authorised against a policy. the power of a zero trust architecture comes from the access policies you define. policies can also help to facilitate risk managed sharing of data or services with guest users or partner organisations.

the policy engine is a key component of the zero trust architecture, it uses multiple signals and provides a flexible and secure access control mechanism that adapts to the resources being requested.

**5. authenticate & authorise everywhere**

authentication and authorisation decisions should consider multiple signals, such as device location, device health, user identity and status to evaluate the risk associated with the access request. we do this as we assume the network is hostile and want to ensure all connections that access your data or services are authenticated and authorised.

**6. focus your monitoring on users, devices and services**

in a zero trust architecture, it is highly likely that your monitoring strategy will change to focus on users, devices and services. monitoring of these devices, services and users behaviours will help you establish their health. monitoring should link back to the policies you have set to gain assurance in their configuration.

**7. don't trust any network, including your own**

don't trust any network between the device and the service it's accessing, including the local network. communications over a network, to access data or services, should use a secure transport protocol to gain assurance that your traffic is protected in transit and less susceptible to threats.

a zero trust architecture changes the way traditional user protections such as malicious website filtering and phishing protection are implemented, these may need to provided by different solutions in your zero trust architecture.

**8. choose services designed for zero trust**

services may not support zero trust and thus may require additional resources to integrate and increase support overhead. in these scenarios it may be prudent to consider alternative products and services that have been designed with zero trust in mind.

using products that utilise standards-based technologies allows for easier integration and interoperability between services and identity providers.

## CIA triad

1. **confidentiality**
2. **integrity**
3. **availability**

**confidentiality**: only authorized systems can view sensitive informatio data sent over the net should not be accessed by unauthorized individuals; an attacker can capture data and gain access to information; a primary way to avoid this is to encrypt data e.g. AES (advanced encryption standard), DES (data encryption standard),VPN

**integrity**: making sure the data has not been modified, corruption of data is  failure to maintain data integrity; hashing functions can be used e.g. SHA (secure hash algorithm), MD5 (message direct 5)

**availability**: the network should be readily available to its users; to ensure availability, the sysadmin should maintain hardware, updates and have a plan for fail-over

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

## authentication

- kerberos
- RADIUS
- LDAP
- SSO
- certificates
- local auth

## understand 

- SIEM
- SOAR
