# Introduction to Security Operations Center
##
This course aims to helps us: 
- Gain an understanding of SOC team member’s daily activities and responsibilities.
- Identify who these bad actors are, their motives, why they attack, and what they attack.
- Review the goals of implementing a SOC and covers the business benefits that an organization achieves by employing a SOC.
- Introduce technical and procedural challenges in a SOC.
##

### Week 1
#### SOC Defined
- A SOC is the first line of defense in preventing and responding to IT security breaches.
- Each member of a SOC team has a specific role with a specific skill set
  - **Tier 1 Analyst:** The triage specialist who must determine whether the alert is justified or simply a false positive.
  - **Tier 2 Analyst:** The incident handler does an in-depthassessment to understand the scope of the attack and identify the affected systems. 
  - **Tier 3 Analyst:** Threat hunter or incident responder is the most experienced member of the SOC operation team.
  - **SOC Manager:** Responsible for leading the SOC. The SOC manager supervises, manages, coordinates the team and provides technical guidance when needed.
  - Some extended SOC Team members include:
    - **Chief Security Officer or CISO** who defines strategies, goals and objectives of the organization's overall security operations
    - **Security Engineer** who develops, integrates, and maintains SOC tools, as well as defines requirements for new ones.

#### SOC Environment Today
- **Dwell Time:** This is the amount of time the cybercriminals have been inside a network prior to detection.
  - Knowing the Dwell time helps to guage how quickly a threats presense is being detected and how long they have had to execute malitious actions.
- The current average time required for a company to detect intrusion is between 100 and 200 days. This is why drills are performed to provide information on how fast a malicious action is detected by a SOC and how fast the SOC can mitigate.
- Cyber criminals come primarily from organized crime. They can also be state affiliated, employees, or even unskilled hackers using tools they obtained online.
- The most common breaches are known as Phishing. Phishing usually involves sending an email falsely claiming to be legitimate. It is usually combined with a threat and request for information such as bank details.
- Ransomeware attacks are often intiated via a phishing attack.
  - I.e. A link to a malicious website is included in an email. The bad actors will attempt to encrypt the hard drives of the targets computers rendering them unusable and the more sophisticated attackers will exfiltrate sensitive corporate data and threaten to publish the data is a ransom is not met.
    
![Attack Continuum](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/J_A_jODNRSywP4zgzTUsZw_7bb2d61f4e2143ad82b5448a21eba6f1_IINS_30_ProtectingNetworkwithFirePOWER_001.png?expiry=1713744000000&hmac=BE4uUeDLZT86jC0oUdG3Q12PISAeB6H7yFMFLlPsjRs)
- Before attacks occur, in-depth analysis of network traffic has been performed to establish a baseline of normal behavior. Policies and controls can then be implemented to properly defend the environment. During an attack, it is critical to detect the presence of malware and block identified threats continuously.
- After an attack, take the following actions:
  - Marginalize the impact of an attack by identifying the point of entry.
  - Determine the scope of the attack.
  - Contain the threat and remediate the infected host.
  - Minimize the risk of re-infection.
 
 #### Goal of a SOC
 Why would a corporation consider employing a SOC?
 - The ultimate goal of any organization using a SOC is to maintain business integrity and continuity. Revenue loss due to downtime is costly and credibility loss due to a breach can be even worse for the company.
What are the strategies that a SOC uses so that an organization can reach these goals?
- First, the SOC team will develop a proactive strategy to reduce the time necessary to respond to a threat. The more they know about their networks, the easier it will be to identify potential attacks. This knowledge will be gained through integration with activities like **asset inventorying, continuouse security monitoring, vulnerability scanning, penetration testing, and treat hunting.**
- Next, the SOC will work to minimize a breach's impact when one does occur. This is done by reducing the time it takes to detect a breach by prioritizing its activities based on current industry threats and the aid of threat intelligence.
  
#### Challenges of a SOC
- **Governance and Compliance:**
- **Information Technology:** IT infrastructures are becoming more complex and interdependent with multiple on-premises and Cloud-based components. This makes it increasingly difficult for the SOC analyst to process and make sense of the different data sources. With the increasing number of devices, more events are generated, which inevitably results in more false-positive alerts.
- **People:** The most important resources that the SOC possesses are its people. The human resource challenges facing the SOC personnel are multifaceted and include the following
  - **SOC Analyst Burnout:** there's a vast number of alerts entering into the SOC constantly. It is a very monotonous task but associated with a high responsibility, and any incorrect decision can lead to serious consequences. A combination of time, pressure, and the monotonous nature of their work can often lead to burnout.
  - **Lack of skilled staff:** Lack of skilled staff and difficult retention. Due to the issues just described, it is difficult for companies to retain skilled staff for their SOC. Companies must spend resources on maintaining the skill level of their current staff or spend additional resources on training new staff members.
  - **Lack of effective communications:**

##

### Week 2
#### SOC Interaction with Other Departments
- SOCs require effective tools, experienced SOC analysts with comprehensive technical backgrounds, and strong relationships with internal and external organizations. Building strong, positive relationships with important business stakeholders is direct and concise communication. The security analyst must identify important resources from IT, networking, and software or database departments when an incident occurs.

#### Common SOC Services
- A SOC offers services that begin before incidents occur and continue to function until after the incidents are resolved. Here you will learn about the various services that a SOC provides throughout the incident response phases. In the following video, you will learn several key functions the SOC provides at these steps, and you will learn the other departments within the organization that the SOC interacts with to perform incident response.

- One of the main responsibilities of a SOC is to find and respond to security incidents. Incidents are alerts or events that could pose a serious threat to the organization and should be escalated to the incident response team.

- Alerts can come from several places and systems, such as the following:
  - *Users*
  - *Helpdesk*
  - *Hardware*
  - *Software*
    
The **SANS (SysAdmin, Audit, Network, and Security) Institute** is the world’s largest provider of security training and certification. SANS defines a six-step plan for incident response and is widely used in the cybersecurity industry for cybersecurity incident response procedures.

- The six steps of the *SANS* incident response plan are the following:
  - **Preparation:** The organization’s security policy is defined. A risk assessment is performed to identify all sensitive assets, and a strategy is then defined to prioritize security incidents based on the risk assessment. Finally, a Computer Incident Response Team (CSIRT) will be established, which is the group that works in responding to computer security incidents.
  - **Identification:** Possible security incidents are identified in this phase. Additional evidence is collected to document the type and severity of each incident’s occurrence.
  - **Containment:** This phase ensures that a confirmed incident does not spread or cause more damage, and that the attacker is unable to access any additional resources.
  - **Eradication:** In this phase, all unauthorized information is completely removed from systems. An example is “bot” software that was used to communicate with a command-and-control server on the internet. If not removed, it could remain latent for a large period and therefore go undetected, only to initiate communication at a later date.
  - **Recovery:** After the incident has been isolated and eradicated, the affected systems are restored to their “normal” state, or as close as possible to this state.
  - **Lessons learned:** In the last phase, determination of the cause of the incident is the focal point. A plan is developed for preventing future occurrences proactively.
 
## 

### Week 3
#### SOC Types and Staffing Considerations

**Threat-centric SOC**
- *A threat-centric SOC* proactively hunts for malicious threats on networks. New threats can be discovered through recently identified vulnerabilities, threat intelligence gathering services, and reported observations detailing malicious anomalies across targeted industry segments.

- Detecting attacks and incidents is a challenging task, even for highly trained security personnel. To deal with today's greatest security challenges, organizations need a simpler, scalable, threat-centric approach that addresses security across the entire attack continuum— *before, during, and after an attack.* 

- *Before an attack*, comprehensive contextual awareness and in-depth analysis of the network traffic are needed to implement policies and controls that properly defend the environment.

- *During an attack*, it is critical to have the ability to continuously detect the presence of malware and block identified threats.

- *After an attack*, the following actions should be taken:

  - Marginalize the impact of an attack by identifying the point of entry.
  - Determine the scope of the attack.
  - Contain the threat and remediate the infected host.
  - Minimize the risk of reinfection.

**Compliance-Based SOC**
  - A compliance-based SOC is focused on comparing the compliance posture of network systems to reference configuration templates and standard system builds. This type of monitoring detects unauthorized changes and existing configuration problems that may lead to a security breach. Typically, such issues cannot be identified by common security tools, such as vulnerability scanners, unless the configuration problem is actively exploited. The best time to identify potential security issues within the network is certainly not during an exploit.

- Linking the risk management and incident response practices of an organization to an automated system compliance process is key to a successful compliance-based SOC. There could be circumstances in which an industry requirement mandates standards-based security practices, such as continuously evaluating against benchmarks established by the Center of Internet Security (CIS) or meeting PCI DSS 2.0 compliance.

**Operational-Based SOC**
- An *operational-based SOC* is an internally focused organization that is tasked with monitoring the security posture of an organization’s internal network. **Tiers 2 and 3 analysts** that work in these SOCs research, develop, and operationalize complex detection techniques that are tailored for an organization's specific network environment. **Tier 2 analysts** may develop highly customized regular expression (REGEX)-based search strings. **Tier 1 SOC analysts** are commonly tasked with deploying these customized REGEX-based expressions into the organization’s *security information and event management (SIEM)* analytic solution. An operational-based SOC is focused on maintaining the operational integrity of the identity management and access policies, intrusion detection system rules, and the administration of firewall *access control list (ACL)* rules. The *Computer Security Incident Response Team (CSIRT)* is the most technically accurate term that describes an operational-based SOC.

- A typical reaction when looking for a solution to a security problem is to enable or configure multiple security-based features on a network security device. However, it is important to understand that operational-based security issues cannot be fully addressed by haphazardly enabling random security features on a device. The inherent risk is that the individual who is implementing these security features may inadvertently misconfigure the device, which can remove features that are meant to protect the organization. Addressing operational issues within an organization requires operational solutions and operational competence.
