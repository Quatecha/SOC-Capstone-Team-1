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

##

### Week 4
#### SOC Roles
- For example, an entry-level analyst  would most likely perform initial triage for alerts that are generated  from a security information and event management tool (SIEM) or an IT  service management (ITSM) ticketing system. After determining that an  alert requires further investigation (based on the SOC’s policies and  workflow procedures), an analyst might escalate the alert to the  investigation team to analyze. The investigation team might collect data  from available tools and perform event correlation on the data to  identify any patterns or relationships. If they determine that more  analysis is necessary, they escalate the alert to a senior member of the  team.
- ![Roles in a SOC](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/4hml_E-sQmOZpfxPrGJjWQ_4658dc657c9d4914b0b31a7ebf8b30a1_CBROPS_1-0-0_DefineSOC_008.png?expiry=1714694400000&hmac=s9TL8mBLHd_w-ZrXAp-akP6vJlO2WciTWocsYt3eLXM)

#### SOC Tasks and Responsibilities Overview
- A SOC team member helps an organization identify the primary effects of cyberattacks. In short, a SOC analyst works to figure out exactly when, how, and even why an attack was successful. To this end, a SOC analyst reviews evidence of attacks. Such evidence is called an *indicator of attack*. If an attack is successful, a SOC analyst will then study *indicators of compromise* to help the organization respond appropriately, as well as make changes so that similar attacks don't happen in the future. All SOC analysts will have a foundation of skills, including device configuration, traffic capture, performance monitoring, and device monitoring. Note that the **Tier 1 analyst** will play the most heavily in these functions.

**SOC Tier 1 Analyst: Triage Specialist**
As the **triage specialist**, the SOC Tier 1 analyst takes these actions:
- Determines the criticality of each alarm or threat
- Prioritizes alarms and alerts based on criticality
- Enriches all threats with relevant data
- Escalates threats unsolved by layer 2 analyst
- Manages and configures security monitoring tools

**SOC Tier 2 Analyst: Incident Handler**
The SOC Tier 2 analyst is the **incident responder.** They will take the following actions: 

- Perform in-depth assessment of incidents escalated by triage specialist.
- Provide attack context through the inclusion of telemetry data not collected by the triage specialist. This may result in discovered actionable threat intelligence to aid in a detection feedback loop through Indicators of Compromise and better rule sets.
- Determine the scope of the attack, the nature of the attack, and the systems affected.
- Decide on a strategy for containment, remediation, and recovery and execute this strategy.
- Decide on a strategy for containment, remediation, and recovery and execute this strategy.
- Escalate to Tier 3 if there are issues encountered.

**SOC Tier 3 Analyst: Incident Responder and Threat Hunter**
The SOC Tier 3 analyst is the **threat hunter** and sometimes also the *subject matter expert*. They are the most experienced in the SOC workforce. The threat hunter takes the following actions:
- Proactively identifies threats, security gaps, and unknown vulnerabilities.
- Researches new attack techniques and models threats relevant to the organization. Recommends optimizations and configurations for use in security monitoring tools and assets.
- Aids the other SOC analysts on major incidents. The threat hunter brings key insights, experience, and expertise to incidence response operations.

**SOC Manager**
The SOC manager is responsible for the following:
- Managing the security team, including hiring, training, and evaluating team members.
- Assessing incident reports.
- Developing and implementing crisis communication procedures:
  - Oversees the financial aspects.
  - Supports security audits.
- The SOC manager reports to the *Chief Information Security Officer (CISO).*

**SOC Tools**
The SOC team uses various tools for different activities. Some of the tools that make up their toolkit include the following:
- **IT Service Management (ITSM)** system is a set of workflow tools that collects and manages incident  data from security tools and devices into a structured automated  workflow that assists the SOC with prioritizing threats. An example of a  popular ITSM is ServiceNow.
- **Security and Information Event Management System (SIEM).** Provides  real-time monitoring, analysis, and logging of events. Provides User  and Entity Behavior Analytics (UEBA) via artificial intelligence (AI)  and machine learning technologies. Splunk is an example of a popular SIEM.
- **Intrusion Detection System (IDS) / Intrusion Prevention System (IPS).** Monitors  networks for malicious activity or policy violations. An IDS will  provide an alert to the SOC analyst on a potential incident. An IPS will  provide an alert to the analyst and will take additional remediation  actions to block the intrusion to minimize damage. An IDS is usually  classified as either *Network Intrusion Detection Systems (NIDS)* or *Host  Intrusion Detection Systems (HIDS).* A NIDS will monitor network traffic  for harmful or abnormal behavior. An HIDS will monitor a single device  or host for harmful or abnormal behavior. Cisco Firepower 4100 Series is  an example of an appliance with NIDS/IPS functionality and Cisco Secure  Endpoint is an example of an HIDS/IPS.
- A **vulnerability scanner**  is an application designed to assess computers, networks, or  applications for known weaknesses. They identify vulnerabilities  resulting from device misconfigurations, software flaws, and missing  software patches that may be present in devices such as firewalls,  routers, and servers, and endpoint devices. Nessus is an example of a  popular vulnerability scan application.
- A **Threat Intelligence** service  collects, processes, analyzes, and disseminates threat information and  responds to activities that pose a threat to applications and systems.  Threat Intelligence collects vulnerability and exploit information in  real time, compiles into a single database, and disseminates it to  consumers of the service. Cisco Talos is one of the largest providers of  security threat intelligence.

**Before, During, and After Incidents**
During the day, the SOC analyst typically  focuses on monitoring. When an incident occurs, the SOC analyst’s  attention turns to incident response and to some of the available tools.  The SOC must coordinate with the stakeholders during the incident.  Working with the network operations center (NOC), system owners, and  data owners can improve the outcome.

The  *SOC Tier 1 triage specialist* focuses on the ITSM ticketing system to  monitor alerts. The threat hunter focuses on the Cisco Talos threat  intelligence feeds.
![Incident Response](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/hJOyGOUcRquTshjlHBarlA_ef2c0c2b3f5640688c3c1ebc5c2a8ea1_SALYST_1-0-0_Preincident-During-Incident_001.png?expiry=1714694400000&hmac=k97ZGUEy9s3y9K6VVBjUYcI_vEKYwWrFrRO4C_j0DVo)

After an incident is resolved, the SOC begins its recovery phase. They work closely with the legal department to make sure all procedures are documented and will hold up in court proceedings. Reports are created that detail findings and lessons learned. The SOC analysts take the following steps in the post-incident phase:

1. Use  forensics applications, such as Encase, Velociraptor, or Redline, to  collect, analyze, and create reports. Also, take steps to help ensure  legal compliance for potential court procedures.
2. Consider using a SOC 2 audit report to show organizational and legal compliance.
3. Generate multiple reports that will serve as lessons learned for future SOC incident response activities.

#### Interaction of Various Roles Within the SOC
In addition to SOC analysts, a security operations center requires a  manager for its many moving parts. The SOC manager often responds to  incidents within and outside the SOC. The SOC manager prioritizes the  work and organizes the resources with the goal of detecting,  investigating, and mitigating incidents that could impact the  organization. The SOC manager determines both the day-to-day activities  and the base skills that the security analyst requires to successfully  perform their job. The SOC manager should develop a workflow model and  implement standard operating procedures (SOPs) for incident management  that guide the analysts through the triage and response procedures.  

A SOC Tier 1 analyst must have foundational  knowledge in basic networking, traffic capture, and device monitoring.  The figure shows how a SOC Tier 1 analyst can take the initial tickets  from the ITSM tool and perform an analysis to see if it requires further  investigation. The initial process could include using multiple  applications and tools to focus on the hosts or devices that are  involved in the alert. The process could also determine whether an alert  is a true positive or a false positive.
![Functional Model for Security Analyst](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/1C_tcjedSJ6v7XI3nXieIw_2f8223ea6ce442aebad320850accffa1_CBROPS_1-0-0_DefineSOC_009.png?expiry=1714780800000&hmac=xn3s5eg29o1MJkhHo3qUVfkwYmdAv_AiCF5t0Xi-r7E)

The SOC tiers can include the following responsibilities:  
- Tier 1:
  1. Monitors the alert queue continuously
  2. Triages security alerts.
  3. Monitors the health of the security sensors and endpoints
  4. Collects data and context necessary to initiate Tier 2 work

- Tier 2:
  1. Performs deep-dive incident analysis by correlating data from various sources
  2. Determines if a critical system or data set has been impacted.
  3. Provides guidance on remediation.
  4. Provides support for new analytic methods for use in threat detection

- Tier 3:
  1. Applies  in-depth technical knowledge about the network, endpoint, threat  intelligence, forensics, malware reverse engineering, and the  functioning of specific applications or underlying IT infrastructure
  2. Acts as an advanced security analyst and proactive threat hunter who doesn’t wait for escalated incidents
  3. Participates in developing, tuning, and implementing threat detection analytics

The  key to building strong relationships with internal stakeholders is  direct, concise communication. It is important for the SOC to identify  critical resources from within the IT, networking, and software  departments in case an incident occurs. The SOC manager communicates  pertinent information regarding the incident to internal parties and  stakeholders, including the CISO or CIO, the legal department, the human  resources and public affairs departments, and the companywide  workforce.

The SOC also has interactions  with external resources. The following are examples of external  resources that the SOC might contact during an incident:
- Legal entities
- Media sources
- International courts of law
- US-CERT/CISA

##

### Week 5
#### SOC Relevant Data and Security Event Data Introduction
When responding to an incident, the SOC analyst must perform an analysis  based on event data types. For instance, the event data type that is  used to display only the source and destination elements of a session  differs from the event data type that represents a full account of all  the data exchanged between two devices on the network.  

The SOC analyst must understand the  attack kill chain process to determine which data they need to examine  during the security incident. 
![Attack Kill Chain](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/zlUWwH04TfuVFsB9OA37Lw_384e7f3c5fa34a53b161ac57746a6df1_1.PNG?expiry=1714780800000&hmac=rGTE9jLwoNzi9cIDUNf7MxI1CB_mk7OVDl3Oq7AqkYU)

**Network Security Monitoring Data Types**
Because  no single data type offers a complete solution, the SOC analyst must  conduct the investigation by analyzing several types of event data:
- Session data
- Full packet capture
- Transaction data
- Extracted data
- Statistical data
- Alert data
- External data

**Session Data**
Session data, or flow data,  communication represents a summarized conversation between two endpoint  devices on the network. In the physical world, a detective might analyze  a phone bill in an investigative process. The phone bill does not  capture any information that was exchanged during a phone call. However,  knowing who called whom at what time and for how long can be useful  during an investigation. 

Session data  is the cyber equivalent of a phone bill in the physical world. Session  data documents all the individual network sessions, based on the  session's 5-tuple (transport protocol, source IP address, source port,  destination IP address, and destination port). Session data includes  time stamps, indicating when the session started and when it ended, and  the amount of data. Depending on the source of session data, other  information can be included with the data. NetFlow-v5, NetFlow-v9, and  IPFIX are commonly implemented data session standards.

**Full Packet Capture**
While session data can be considered  analogous to a phone bill, a full packet capture can be considered  analogous to a wiretap. A full packet capture consists of the header and  the entire payload of a packet. The full packet capture represents a  full account of all the data exchanged between two devices on the  network. 

The header contains metadata,  such as the packet’s source and destination IP address. The payload  contains all the data exchanged. The actual content of a conversation  can be extracted from full packet captures. From that perspective, a  full packet capture might seem superior to session data.

However,  a full packet capture has downsides. Compared to session data, it has  tremendous storage requirements. It can also be tedious to analyze.  Usually, an analysis that is performed with higher-level data types is  required for effectively guiding the analyst to relevant portions of  full packet capture data. 

There are  various file formats for storing full packet capture data. The most  commonly used file format is the packet capture (PCAP) file extension.

**Transaction Data**
Transaction data highlights operations  that occur as a result of network sessions and system activities. For  example, an HTTP daemon software program running on a web server might  produce log files that document all the client requests that it  receives, along with its own responses to those requests. An SMTP daemon  might produce log files to document connections from other SMTP  systems. The log files might also document the forwarding of email  messages to other SMTP systems and the storage of email messages in  local mailboxes. A Linux system might produce a log file that documents  all operating system login and logout activities.

Each  log file contains transaction data. Note that there is not a one-to-one  relationship between session data and transaction data. An individual  network session might not produce any transactions or might be  associated with several transactions. Transactions can also document  local activities on a system that do not involve network communications.

**Extracted Content**
Artifacts that are mined from network  traffic are considered extracted content. Such content includes, for  example, files that are transmitted as email attachments or files that  are downloaded from a website. Some security monitoring systems pull  extracted content from live network streams. With other security  monitoring systems, you can mine the extracted content from full packet  capture (PCAP) files. The artifacts may also be smaller pieces of data,  such as particular strings defined by an analyst query.

Artifacts that may be extracted include the following: 
- **Sessions:** Session  data about all network connections, including the standard IP 5-tuple,  time stamp of the session start, and frame number within the PCAP where  the session starts.
- **DNS:** Transaction data documenting all DNS requests and replies.
- **Hosts:** All  IP addresses that are seen in the PCAP along with other relevant  information that can be gleaned from the PCAP. Potential information  includes DNS hostnames, open TCP ports, operating system, sessions that  are associated with the host, and total packet and byte counts that are  associated with the host.

**Statistical Data**
Statistical data aggregates other  security monitoring data types. This action aids in describing network  activities at a higher level. Statistical data is used to baseline  network traffic activity. 

NetFlow  session data documents each individual connection to a web server. A  graph can be produced using NetFlow session data that shows the average  number of connections per minute to the web server over a period of a  month, The graph is considered statistical data that can be used to  formulate a monthly report identifying baseline network traffic activity  to and from the web server. Baseline data queries document the  aggregate normal network traffic patterns and their trends. Comparing  actual traffic patterns to the baseline patterns can reveal anomalous  behavior. Two common statistical data queries are baseline graphs and  top reports.

Top reports can answer questions such as the following:
- Which hosts request the most HTTP data?
- Which hosts serve the most HTTP data?
- Which DNS domains are the most requested?

**Alert Data**
Alert data is the most formed of the  data types. Alert data is generally produced by an IDS or IPS system.  These systems use complex mechanisms and data sources to monitor traffic  streams for malicious behavior. Alert data is generated when network  traffic or some other type of data matches a set of rules that are  configured in a tool. The greatest benefit of alert data is that it is  created after the tool analyzes large sets of data that otherwise must  be analyzed manually by a SOC analyst.

Despite  being the most formed data type, alert data is not necessarily the most  accurate or most relevant data type. The alert is a judgment call that  is produced by a tool. False positives and false negatives are potential  issues with alert data. The advantage of alert data is that the tool  can process tremendous amounts of network traffic in real time. It is  faster than a human analyst could ever be. However, the production of an  alert is often only the start of the analysis. SOC analysts are the  primary recipients of this type of data and must analyze it to judge its  disposition. The SOC analyst determines whether the alert is a false or  true positive.

**External Data**
External data consists of information from outside the organization.  External data is knowledge and information about existing or emerging  threats that an organization can use to proactively respond to those  threats. This knowledge is based on the analysis of input data that is  collected from various internal and external sources. For an  organization to be aware of the latest threats, it must subscribe to  threat intelligence feeds. Threat actors are constantly making  improvements to their malware to avoid detection. Therefore, the SOC  must make constant improvements to the threat detection systems,  including creating and refining rules and signatures or adding new  detection capabilities. Intelligence feeds help the organization to  proactively defend against attacks. SOC analysts incorporate actionable  data from the feeds into indicators of compromise (IoCs) and artifacts  that improve the fidelity of the alerts and provide greater context.  

#### SOC Tools and Their Features
A SOC relies on a supporting infrastructure of tools and systems that provide the following services:
- Network mapping
- Network monitoring
- Vulnerability detection
- Penetration testing
- Data collection
- Threat and anomaly detection
- Data aggregation and correlation
- One tool that is used by analysts in a SOC is *Security Onion.*

**Security Onion** is intended to support SOC analysts with a suite of tools for network security monitoring, including intrusion detection, network security monitoring, and log management. The Security Onion distribution is based on the Ubuntu Linux operating system and contains several useful security tools that are designed to provide four core network security-monitoring functions as follows:
- Full packet capture
- Network-based and host-based intrusion detection sensors
- Security analysis tools
- Log management

The **Enterprise Log Search and Archive** (ELSA) version of Security Onion is composed of the following tools: 
- **ELSA:** ELSA is a centralized syslog framework that is built on Syslog-NG, MySQL, and Sphinx full-text search. It provides a fully asynchronous web-based query interface that normalizes logs and makes searching billions of them for arbitrary strings as easy as searching the web. It also includes tools for assigning permissions for viewing the logs, email-based alerts, scheduled queries, and graphing.
- **Snort:** An open source, rules-driven network intrusion detection system (NIDS) and network intrusion prevention system (NIPS) developed by Cisco (Sourcefire). It performs real-time threat detection and generates alerts when threats are detected. The NIPS inline mode is not supported within Security Onion.
- **Suricata:** A script-driven NIDS and NIPS threat detection engine for analyzing traffic and generating alerts. NIPS inline mode is not supported within Security Onion.
- **Zeek (Bro):** A packet recorder and protocol parsing engine that is commonly used to analyze network traffic to detect behavioral anomalies.
  - **Traffic logging:** Traffic captured by means of SPAN, a TAP port, or a packet broker. Traffic logging generates comprehensive, protocol-specific traffic logs for more than 35 network protocols and application layer analyzers, including HTTP, DNS FTP, and SMTP.
  - **Automated analysis:** Traffic analysis that uses Bro scripts.
  - **File extraction:** Extracts and reassembles various file types directly off the wire.

- **Wazuh (OSSEC):** Host-based intrusion detection system (HIDS) that replaced OSSEC and is used to monitor and defend Security Onion. Wazuh offers a lightweight monitoring agent that can be installed on network host devices and is supported on Windows, Linux, Mac OS X, HP-UX, AIX, and Solaris platforms.
- **Netsniff-ng:** Captures network traffic via SPAN, a TAP port, or packet broker in the form of PCAP files.
- **Sysmon:** Windows system service to monitor event log and system activity.
- **Syslog-ng:** An enhanced BSD log daemon that can receive logs and collect inputs from a wide range of sources.

**Network analyst tools:** Provide packet capture and network traffic IP flow analytics capabilities that can be used to find anomalous network activity. The following popular network analyst tools are included within Security Onion:
- **Wireshark:** Network protocol analyzer
- **Sguil:** Sguil (pronounced "sgweel") is built by network security analysts for network security analysts. Sguil's main component is an intuitive GUI that provides access to real-time events, session data, and raw packet captures. Sguil facilitates the practice of Network Security Monitoring and event driven analysis.
- **Squert:** Squert is a web application that is used to query and view event data that is stored in a Sguil database (typically IDS alert data). Squert is a visual tool that attempts to provide additional context to events by using metadata, time series representations and weighted and logically grouped result sets.
- **NetworkMiner:** Performs network traffic analysis for parsing PCAP files and extracting artifacts
- **CyberChef:** Web-based application for data manipulation
- **CapME:** Helps with analyzing PCAP transcripts and downloading captured PCAP files

##

### Week 6
#### Internal Stakeholders
Although the SOC team members are highly  skilled cybersecurity professionals, they must engage personnel in the  organization’s other departments to carry out their incident response  efforts. These personnel are known as internal stakeholders. They  provide the necessary expertise and guidance during an incident  response.

Internal stakeholders range  from human resources to legal department personnel. It is important for  you to learn how to identify the internal stakeholders. It is also  important to look at their responsibilities and interactions with the  SOC team during an incident response. You will need to consider the  rules of engagement that the SOC will use when seeking their assistance.  The organization will have to define the information escalation process  that will be followed during an incident response by following the  established incident management communication plan.

#### External Stakeholders
An organization might be obligated to divulge information to certain  external bodies, more commonly known as external stakeholders, when a  cybersecurity incident occurs. It’s important for the organization to  build relationships and to establish effective practices for  communicating with external stakeholders. Cybercrime incidents are  always unplanned and cannot be predicted. Therefore, incident management  communication often occurs quickly and unexpectedly and the  organization must predetermine the appropriate information to share with  each external stakeholder before an incident. During the first phase of  the incident response, the organization engages with their computer  security incident response team (CSIRT). The organization assigns a  point of contact (POC) to interact with external stakeholders. The POC  and incident response team must follow the organization’s policies and  guidelines for interacting with external stakeholders. The  organization’s legal department must also be consulted before  information is shared with external stakeholders.  

##

### Week 7
#### Security Data Aggregation
A SIEM is used by most enterprises to provide real-time reporting and analysis of security events. The SIEM collects, sorts, processes, prioritizes, stores, and reports the alarms to the security analyst. One of the main goals of using a SIEM is to reduce the time that is needed to detect, and to contain the threats. For example, if an employee laptop becomes infected by malware, the infected laptop may try to discover other systems on the network and then attempt to attack those other systems, spreading the infection. Each system under attack may be running some host-based security controls, which can report the malicious activity to the SIEM. The SIEM can correlate those individual events into a single alert that identifies the original infected system and its attempted targets. The infected systems then can be isolated from the network until the malware is removed. 

The SIEM can provide information in both real-time alerts and historical reports that summarize the security status over time, typically on the order of months rather than days. This historical perspective enables the security analysts to establish a baseline of their SOC operations. The SIEM and its back-end storage must be properly sized and perform at a reasonable level. Two major factors that affect the volume of data in a search are the total size of log data coming from the different systems, and the time range of the search query.

Deploying a SIEM as a project is not as simple as racking a new box of SIEM hardware and expecting it to work. It is important to understand and follow all the proper deployment planning steps. Scope, business requirements, and engineering specifications are all factors in determining the success of the SIEM project.
![SIEM](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/pk2k2Q2kTWWNpNkNpG1l8w_1f3d9c97ac3c45a9b760f608e71182f1_CBROPS_1-0-0_SOCMetrics_001.png?expiry=1714780800000&hmac=tD0lsFYGwoBPWir6pAKMGwyWYJXg4c0iQ3_rDu9ycuc)

The main SIEM functions include:
- Log collection of event records from sources throughout the organization
- Log normalization to map log messages from different systems to a common data model
- Events and logs correlation to speed the detection of and reaction to security threats
- Consolidating duplicate event records to reduce the volume of event data to be analyzed
- Reporting tools to address regulation compliance reporting requirements

The SIEM is intended to be the glue for various security tools. Many Open Source and closed-source SIEMs are available in the market. Vendor-specific SIEMs, such as Splunk, may also contain some Open Source components. All the Splunk Open Source projects are hosted on GitHub.

#### Time to Detection
As stated in a Cisco Annual Security Report, the current industry estimate for time to detection (TTD) is 100 to 200 days, which is clearly an unacceptable time frame given how rapidly malware authors are able to innovate. The time that it takes for businesses to detect a data breach once it occurs gives the threat actors plenty of time to conduct surveillance and steal the sensitive data of a company. Defenders must adopt strategies and implement solutions that provide end-to-end network activities visibility and reduce the TTD. For example, the Cisco CSIRT, using a combination of people, processes (such as the incident response process), and technologies (such as Cisco Advanced Malware Protection [AMP]), reduced the TTD from days to hours.
![Time to Detection](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/zgr6_u08StuK-v7tPFrb8w_e2217114560f4bb8bc994d0d1c795cf1_1.PNG?expiry=1714780800000&hmac=nc79VcdZVVGsWzzk3e31I8Pb-ymkPuczf9zUVefUuD0)

According to another cybersecurity report conducted by the Ponemon Institute, once a data breach occurs, it takes an average of 98 days for financial services companies to detect intrusion on their networks, and 197 days in retail. Despite the long time to detection, also known as dwell time, 58 percent of people who work in finance and 71 percent of people who work in retail said that they are not optimistic about the ability of their firm to improve these results in the coming year.

While there are varying views on TTD, Cisco defines TTD as the window of time between the first observation of a malicious event having bypassed all security technologies and make it to an endpoint, and the detection of a threat that is associated with that malicious event.

As part of the incident response process, after the detection phase, should come the containment and mitigation phases. Similar to the TTD, other important metrics for measuring the effectiveness of the SOC include the time to containment, and the time to mitigation.

#### Security Controls Detection Effectiveness
Effective security controls that work  across the attack continuum can help reduce the TTD. An effective  security control should produce true positive events, few false positive  events, and most importantly, minimal false negative events.

All decisions of security controls can be classified as one of the following:
- **False negative:** The  security control did not detect actual malicious activity. Minimizing  false negatives should be given a very high priority, sometimes at the  expense of higher occurrences of false positives.
- **False positive:** The  security control acted as a consequence of benign (nonmalicious)  activity. Many false positives can significantly drain the SOC  resources.
- **True negative:** The security control has not acted, because there was no malicious activity, which represents normal and optimal operation.
- **True positive:** The security control acted as a consequence of malicious activity, which represents normal and optimal operation.

#### SOC Metrics
Today, most enterprises spend more than US$100 billion annually on cybersecurity tools, processes, and people, but history has proven that spending does not always mean secured outcomes. An effective threat-centric SOC consists of deep expertise with cutting-edge technology, leading security intelligence data, and advanced analytics to detect and investigate threats with great speed, accuracy, and focus.
- **Speed:** Faster detection and targeted mitigation reduce the mean time to respond.
- **Focus:** Higher fidelity reduces false positives and ensures proper containment and actionable recommendations for remediation.
**Accuracy:** Continuous monitoring and investigation plus full packet capture illuminate security blind spots. Reasons to use metrics to define and measure SOC effectiveness include the following:

Typically, the job of the CSO is to find the appropriate reporting model for measuring and reporting the effectiveness of the SOC operations and value that fits the organization. The different metrics that are used to measure the SOC should be as specific, measurable, attainable, relevant, and timely as possible. Metrics is a group of measurements that produce a quantitative picture of something over time.  

Over time and as SOC operations mature, the mean time to detect should begin to trend downward, as shown in the figure. A continued decrease in the TTD is a direct correlation of a successful and mature SOC. It may be years before the metric shows success; the SOC does not mature overnight.  

Typical SOC metrics that demonstrate the SOC's value to the business may include:
- The mean TTD of the incident after its occurrence
- The mean time to contain the incident after its detection
- The mean time to mitigate the incident after its containment
- The number of incidents being detected, contained, and mitigated
- The percentage of the discovered incidents found using the plays in the SOC playbook
- The number of new plays added to the SOC playbook
- The number of zero-day attack detections
- The false positive or true positive detection rate
- The operational cost of running the SOC

Regarding the timeline of the incident, the following figure is another linear approach to measuring the incident response process. The example includes the critical metrics that business decision-makers are most concerned with. The time to report the incident is also included in the dwell time.

![Critical Metrics](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/B3rR9TTmQ3-N6yHTN2p0FQ_28c2baf9e89c4cf89a833008747604f1_M2CPcyecSG-gj3MnnEhvqA_d76690da8a1d492ab2f8fe3e6a3873f1_CBROPS_1-0-0_SOCMetrics_006.png?expiry=1714780800000&hmac=SvK7etnXaeiEzldVgAbMniARtBRObPQKHq9DJ1az9EM)

Metrics are essential for the success of any SOC organization. Metrics allow leadership to make decisions that are based on data and facts, and allow for the removal of emotion and anecdotes from critical decision-making processes. By implementing a SOC that is built around the metrics, the leadership will be able to show the maturation of the organization and processes, pinpoint areas of focus for process improvement, identify gaps in prevention, and detection and operational capabilities. An organization without a metrics program will open up the possibilities to misdirect spending and ultimately, when dealing with APT, these decisions can lead to substantial impact. 

##

### Week 8
#### Understanding SOC Workflow and Automation

**SOC WMS Concepts**
A security analyst needs to look at many logs for security and networking tools. Traditionally, analysts must log in many different security and networking devices to review and analyze logs for security incidents. With each log, an analyst needs to review events that are being produced at a rate of a hundred events per hour, or per minute, or possibly per second. It is very difficult for the analyst to effectively analyze all the events without the help of some automation.

Many networking and security logs can be consolidated into a syslog server so that the security analyst can review logs in one place, without having to log in to numerous devices. A syslog server makes it easier for the analyst to manipulate and review logs. However, significant problems still arise when correlating similar events between devices: the logs are not in the same format and do not contain the same types of data; date and times can look different; computer names use different formats; some logs will not have system names or domain names or IP addresses and MAC addresses may or may not be included.

In the last 10 years or so, SIEM security devices have come on the market and greatly changed the way that incidents are identified. When a possible incident is identified, it might take several hours to research by connecting to other security, networking device, and endless endpoints. Analysts would need to be skilled in the use of several of the different devices and have a good understanding of the network, including understanding the path that each type of packet would take through the network and from which device to retrieve logs. With introduction of SIEM, many (if not all) logs from the security and networking devices and endpoints go directly into SIEM. SIEMs are designed to “ingest” logs: The logs are aggregated and normalized.

The role of the security analyst is to follow the established workflow to ensure that incidents are processed efficiently and in the same way. Many repeatable job tasks can be automated to improve the SOC efficiency. 

**Definition of WMS**
A WMS is software that tags and identifies an existing security event, tracks the event, and tracks the actions that are taken in dealing with those events, from detection to response to mitigation to ticketing closure.

A WMS is a platform for orchestrating and automating incident response processes. In simple terms, a WMS automates the remediation of a malicious action. It performs containment and eradication. A WMS does not identify incidents, collect evidence, or help with approvals, which are features of SIEM and a ticketing system.

After a ticket has been created or SIEM has identified an incident, the Tier 1 analyst has collected supporting evidence, and a higher-level tier analyst has confirmed that it is an incident, the security WMS gets involved.

**Workflow Types**
A SOC uses workflows to coordinate tasks between people and synchronize data between different systems, with the ultimate goal of improving SOC efficiency and responsiveness.

There are three types of workflows:
- **Sequential:** A sequential workflow is typically flow chart-based. It progresses from one stage to the next and does not step backward.
- **State machine:** A state machine workflow progresses from state to state. It is more complex and can return to a previous point if required.
- **Rules-driven:** Implementation of a rules-driven workflow is based on a sequential workflow. The rules dictate the progress of the workflow.

A workflow can be described simply as the ordered execution of tasks through a well-defined and structured process. Workflows can be a sequential progression of work activities or a complex set of processes each taking place concurrently and eventually affecting each other according to a set of rules and roles. The WMS defines and controls the various tasks and activities that are associated with a process. In addition, many management systems can also measure and analyze the execution of the process so that continuous improvements can be made. The SOC management team develops the workflow model that implements the standardized operating procedures for the incident handling process. The workflow model guides the SOC analysts through the triage and response procedures. 

**Repeatable Tasks**
Within a live security operations environment, many tasks are performed at defined intervals, and they are repeatable. Most of these tasks are performed by junior staff members. A WMS can automate these tasks to ensure that staff members focus on those tasks that require more cognitive skill sets. Repeatable tasks within a SOC that a WMS can automate can be grouped (at a high level) as follows:

Task & Description
- **Audit log collection and enrichment**
  -The process of retrieving and enriching audit log data from all the devices within the organization as part of SIEM.
- **Look up user information**
  - Querying the Active Directory of an organization or other user repositories to extract further details about the user, such as their department, job title, and so on.
- **Look up device information (IP, hostname)**
  - Querying the DNS records of the organization to obtain corresponding information regarding a device (IP address or hostname). Also, these activities include querying the asset database of the organization for further details on the asset.
- **Notifications and alerts**
  -Generating alerts that are based on specific conditions that are configured within SOC security products and are being monitored by security analysts.
- **Threat intelligence**
  - Using external threat feeds within a SOC to review and research threats that are applicable to the organization based on specific parameters, such as the industry that the organization operates within, financial budgets, and the amount and type of data that the organization collects and stores.
- **Ticket management**
  - Managing tickets within a SOC from creation to validation to resolution and closure.
- **Callouts and escalations**
  - When an alert is triggered, a triage process dictates how to manage the alert. After the alert is confirmed to be an incident, the incident management and response process is initiated. The incident management and response process trigger the need to initiate callouts, contact the appropriate personnel, and at times, trigger callouts to law enforcement agencies.


#### Incident Response Workflow
Maintaining consistency within an incident response process is very important. A defined incident response process articulates how a particular incident is to be handled based on its severity. The key to a sound and robust incident response process is to ensure that all incident severity levels have a defined response process. Also, as an incident is handled, the severity of that incident may change over time. The severity of an incident may be lowered, particularly when an incident is being monitored after remediation. The incident response process should have appropriate procedures in place to identify how an incident should be handled when the severity of the incident is changed from one level to another. 

![Incident Response Workflow](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/qVTZO1hxQMGU2TtYcZDBhA_05c29386442c42f99a684db5d8f16ef1_CBROPS_1-0-0_IRWorkflow_001.png?expiry=1714780800000&hmac=dwSjUDe_A70Fyr6YiKArgXi8lPSiwOnG29uzLLXWWIA)

During an incident response, it is also important to ensure consistent and timely reporting. Each incident severity type would have defined times for notification, constant reporting until an incident is remediated, and monitoring and reporting on the incident after remediation. At times, incident investigators are responsible for the consistent and timely reporting of an incident. As staff work shifts end, these activities are usually handed off to the person on the next shift. Because of the manual nature of this involvement, there are opportunities for investigators to miss reporting targets.

A SOC WMS can automate these types of activities, reducing manual intervention within the incident response process and in ensuring consistent and timely reporting. A SOC WMS can also generate alerts when a certain reporting period is passed, to inform the investigators or confirm if the report for that time period has been acted on.

**Incident Response Workflow Roles**
Within a SOC, there are varying degrees of specialized individuals who are highly trained in the functions that they perform. The figure presents a conceptual overview of the SOC workflow that is focused on the different roles. Organizations will customize their workflow, which is based on their particular situation

![SOC Processes and Tools](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/L7AqprrIRH6wKqa6yLR-Sg_3b243353b7524fc390622760c1a26ef1_CBROPS_1-0-0_workflow_007.png?expiry=1714780800000&hmac=-wOP22DXf8EAYNOmz5Pt3p8DND0K_o0bVh5Kvy5A1LA)

Depending on how the particular SOC is organized, various tiers of security analysts and teams may be involved in the workflow. For example, security analysts may be more involved in the detect and triage stages, while the CSIRT team members may be more involved in the respond stage. Each organization may embed a different variation of a SOC. The following roles would often be found within a SOC:

**Role & Description**
- **Tier 1 analyst**
  - Continuously monitors the alert queue; triages security alerts; monitors health of security sensors and endpoints; collects data and context necessary to initiate Tier 2 work
- **Tier 2 analyst**
  - Performs deep-dive incident analysis by correlating data from various sources; determines if a critical system or data set has been affected; advises on remediation; provides support for new analytic methods for detecting threats
- **Incident response handler**
  - Manages the incident; executes containment strategies and ensures that the incident response process is followed throughout; at times, may also communicate with the business to provide periodic updates
- **Forensics specialists**
  - Focused on gathering, retaining, and analyzing computer-related data for investigative purposes, in a manner that maintains the integrity of the data
- **Malware reverse engineering specialists**
  - Analyze the malware behaviors in depth to determine the relevant tactics, techniques, and procedures, and the indicators of compromise. May also write signatures to detect, hunt, and prevent the malware
- **SOC management**
  - Manages resources to include personnel, budget, shift scheduling, and technology strategy to meet SLAs; communicates with management; serves as the organizational point person for business-critical incidents
- **Executive**
  - Provides overall direction of the SOC; ensures that the SOC is achieving and maintaining the objectives that have been defined



















































