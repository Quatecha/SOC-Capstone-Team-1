#<h1 align="center"> Blue Team SOC-Capstone-Packet Patrol
Group Capstone project repository for Security Operations Center (SOC) implementation.
##
**[Project Requirements](https://docs.google.com/document/d/1EZNmVznhNWx1f6MrD1Wel16jqEMmvVfN-b0MNJu0puU/edit)**

##
- **Team Members Role:**
   ##
  
     • Quatecha Cleveland-Webb: **Team Leader**

     • Margaret Edwards: **Project Manager**

     • Ivan Castillo: Technical Documentation 

     

  
##
Welcome to the SOC-Capstone-Team1 GitHub repository! This project aims to design, deploy, and configure a scalable and automated Security Operations Center (SOC) on a cloud platform in AWS. Our goal is to centralize security monitoring, incident detection, and response capabilities, catering to the needs of Security Operations Professionals, IT Security Teams, and Security Analysts.
##

- **Our target audience includes:**
  
  - Security Operations Professionals
  
  - IT Security Teams
  
  - Security Analysts


#

- **Resources:**
  - [Cloud Security Architecture An Introduction (2024) Full course](https://www.youtube.com/watch?v=RjLM50USrvY)
  - [Security Operations Center (SOC) Coursera](https://www.coursera.org/learn/security-operations-center-soc)
  - [Learn how to Streamline and Enrich your SOC Workflow with Modern SIEM](https://pages.awscloud.com/rs/112-TZM-766/images/AWS_Marketplace_SEC_NextGenSIEM_Whitepaper_Final.pdf?aliId=eyJpIjoiZGJ5SWlNMDVEeUpWU1RVUyIsInQiOiJXRHNUUDFpWklvZVBySHZcLzFzdm9Gdz09In0%253D)
  - [Control access to platform using SOC roles, environments, and permission groups](https://cloud.google.com/chronicle/docs/soar/admin-tasks/advanced/control-access-to-platform)
  - [SOCs: Security Operation Centers Explained](https://www.splunk.com/en_us/blog/learn/soc-security-operation-center.html)
  - [Building a Virtual Security Home Lab: Part 1 - Network Topology](https://infosecwriteups.com/building-a-virtual-security-home-lab-part-1-network-topology-a373f93e342b)
  - [The Five Step SOC Analyst Method](https://cybernoweducation.medium.com/what-is-the-soc-analyst-method-e1ab043d96d3)
##

##
[**Sprint 1: Project Planning & Requirements Gathering:**](https://docs.google.com/document/d/19wsBtw-bw78XlkGJ8Kh6ISsYmWZ57OPBM5P6TyHfUp4/edit)
- [Github Projects for team Collaboration](https://docs.google.com/document/d/1ri4l8PPLV0UcBY9brIH37BRxOGFAiPArHI49kHkJD4o/edit?usp=sharing)
- **Tools Being Used**
  - Wireshark
  - Wazuh
  - Snort
  - pfSense
  - AWS
    - EC2
    - IAM
    - VPC
  - GitHub Projects
##

#
[**Sprint 2: Secure Cloud Infrastructure & Access Control:**](https://docs.google.com/document/d/1IZpg-4bLl94O2m6R04q3y4Obew1XGjvGLFphgxRXlto/edit)
- **Tools Being Used**
  - AWS Identity and Access Management IAM
  - Multi-factor Authentication
  - AWS Virtual Private Cloud VPC
  - AWS Security Groups
  - AWS NACLs
  - AWS Route Tables
  - AWS Cloudtrail
## 

#
 [**Sprint 3: Data Collection & Aggregation:**](https://docs.google.com/document/d/1FfdHndfPya83mZ6Z1iIQR9gHgkQQS28gA9CioG3f_DQ/edit)
- **Tools Being Used**
  - AWS EC2 Instance
  - Wazuh
  - Metasploitable
  - Putty
##

#
 [**Sprint 4: Security & Alert Correlation:**](https://docs.google.com/document/d/1bEoA4FTASEn1FEr4lhsKIP055ClVs7AJno3N_jx78Bw/edit)
 - **Tools Being Used**
   - Security Orchestration Automation and Response tool SOAR
   - Shuffle webhook
   - Incindent Response Playbooks
   - SIEM Solution
   - Correlation Rules and Threat Detection
   - Amazon S3 Bucket
  ##

  #
  [**Sprint 5: Final Deliverables of Cloud-based Security Operations Center**](https://docs.google.com/document/d/1EL0rNWQW0_xBT_Yaeu61LvqEM1sErOSpcF9NzgBBZas/edit)
  **Includes:**
   -  Network Topology
   - Secure Cloud Infrastructure & Access Control
   - The Hive Installation
   - Shuffle Installation
   - 1750 word APA Paper
      
  ##
  #

# Documentation
[IAM](IAM.md)<br>
[VPC](VPC.md)
[Billing and Cost Management](Billing-Cost-Management.md)<br>
[CloudTrail](CloudTrail.md)<br>
[EBS](EBS.md)<br>
[S3](S3.md)<br>
[Kali](Kali.md)<br>
[Metasploit](Metasploit.md)<br>
[Wazuh Manager](Wazuh-manager.md)<br>


The following file is meant to assist in the maintenance and troubleshooting of the project's components:<br>
[maintenance](maintenance.md)




# NOTES
While following this guide, you’ll want to change the fake IPv4 IP address `203.0.113.5` to the stated public or private IP for your instance. This is a fake IP address reserved for demonstration purposes.

The commands/output/code provided in this documentation is often preceded by a `$`.<br>
This is meant to mimic a marker for terminal prompt.<br>
When copy/pasting these commands, do not include the `$`.<br>
Including it will probably throw an error.
