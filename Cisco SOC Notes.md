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
  - Tier 1 Analyst: The triage specialist who must determine whether the alert is justified or simply a false positive.
  - Tier 2 Analyst: The incident handler does an in-depthassessment to understand the scope of the attack and identify the affected systems. 
  - Tier 3 Analyst: Threat hunter or incident responder is the most experienced member of the SOC operation team.
  - SOC Manager: Responsible for leading the SOC. The SOC manager supervises, manages, coordinates the team and provides technical guidance when needed.
  - Some extended SOC Team members include:
    - Chief Security Officer or CISO who defines strategies, goals and objectives of the organization's overall security operations
    - Security Engineer who develops, integrates, and maintains SOC tools, as well as defines requirements for new ones.

#### SOC Environment Today
- Dwell Time: This is the amount of time the cybercriminals have been inside a network prior to detection.
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


