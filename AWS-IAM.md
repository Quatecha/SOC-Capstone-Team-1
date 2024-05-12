# AWS IAM

IAM is the AWS core infrastructure service which is used to provide users or applications fine-grained controlled access to what they can do with which service. It can also be used to create templates that users or applications can temporarily assume.

In this guide, you'll be creating users and roles with *Principle of Least Privilege* in mind.


## Roles
**AWS Console Home Page**<br>
In the Search bar, type `IAM`.<br>
Click on the **IAM** service.

### What are the roles?
For this SOC environment, you'll be creating four new roles, with the following permissions:

* SOC Analyst:  AmazonEC2ReadOnlyAccess, CloudWatchReadOnlyAccess<br>
Grants read-only access to AWS services and resources, allowing SOC analysts to view configurations, logs, and other information for monitoring and analysis purposes without the ability to modify resources. This policy should include permissions to list EC2 instances, VPC configurations, IAM users, and CloudTrail logs.

Access to Monitoring and Alerting Tools: Grant permissions to access monitoring and alerting tools such as CloudWatch, GuardDuty, and CloudTrail. This includes the ability to view metrics, set up alarms, and access log data for security monitoring and incident detection purposes.<br>
Limited EC2 Permissions: Provide permissions to start and stop EC2 instances for troubleshooting purposes. However, limit the ability to modify or terminate instances to prevent accidental or malicious actions.

* SOC Engineer:  SecurityAudit<br>
Grants permissions necessary for performing security-related operations, including access to CloudTrail logs, Config history, and other security monitoring tools. This policy is suitable for SOC engineers who need to investigate security incidents and make configuration changes to improve security posture.

Full Access to Monitoring and Alerting Tools: SOC engineers may require elevated permissions compared to analysts to configure and manage monitoring and alerting tools effectively. Grant them permissions to create and modify CloudWatch alarms, configure GuardDuty settings, and access detailed CloudTrail logs for forensic analysis.<br>
Limited EC2 and VPC Permissions: In addition to the permissions granted to analysts, SOC engineers may require permissions to manage EC2 instances and VPC configurations for deploying security tools and performing network analysis. However, restrict permissions to sensitive actions such as instance termination and VPC deletion.

* SOC Manager:  IAMReadOnlyAccess, AWSCloudTrailReadOnlyAccess<br>
Provides read-only access to IAM resources and CloudTrail logs, allowing SOC managers to oversee user permissions, audit trails, and compliance-related activities without the ability to modify resources directly. Additionally, you may want to customize permissions based on specific managerial responsibilities.

Admin-Level Access: SOC managers may need broader access to AWS resources to oversee SOC operations and manage security incidents effectively. Assign them IAM policies with administrative-level permissions, such as the AWS managed policy "AdministratorAccess" or a custom policy with equivalent permissions.<br>
Full Access to Security Tools: Provide SOC managers with full access to security monitoring and management tools, including the ability to configure and fine-tune settings for CloudWatch, GuardDuty, and other security services.
Limited IAM Permissions: While SOC managers require administrative access to AWS resources, limit their IAM permissions to prevent unauthorized changes to user accounts, roles, and policies. Grant permissions only for IAM actions necessary for managing user accounts and access permissions within the SOC team.

* SOC Administrator:  AdministratorAccess<br>
Grants full access to all AWS services and resources, allowing SOC administrators to perform tasks such as provisioning resources, managing IAM users and roles, configuring security settings, and responding to security incidents effectively. This policy should be assigned with caution due to its broad scope of permissions.

IAM Management: Assign IAM policies that allow SOC administrators to create, modify, and delete IAM users, groups, roles, and policies as needed. This includes permissions to manage user passwords, access keys, and MFA devices.<br>
VPC and Security Group Management: SOC administrators may require permissions to manage VPC configurations and security groups for network segmentation and access control purposes. Grant them permissions to create and modify VPCs, subnets, route tables, and security group rules as necessary.

### Creating the roles
From the IAM Dashboard side panel:<br>
Click on **Roles**<br>
Click on **Create role**<br>
Trusted entity type: **AWS account**<br>
An AWS account:  **This account**  |  **Require MFA**
* This specifies that the role can only be assumed by IAM users of this account.
* It requires MFA for additional security.
Click **Next**


**Add Permissions** page<br>
You can add whichever AWS managed permissions you want to attach to the role.<br>
You'll be typing which AWS managed policies you'd like to add to the current role.<br>
Here are the AWS Managed Policies that each role should have:
* SOC Analyst:  AmazonEC2ReadOnlyAccess, CloudWatchReadOnlyAccess
* SOC Engineer:  SecurityAudit
* SOC Manager:  IAMReadOnlyAccess, AWSCloudTrailReadOnlyAccess
* SOC Administrator:  AdministratorAccess


**Name, review, and create** page<br>
**Role Details**<br>
Role name:  **SOC_Analyst**  |  **SOC_Engineer**  |  **SOC_Manager**  |  **SOC_Administrator**<br>
Select trusted entities:  here you can edit the policy to allow the user to assume the role.<br>
Click **Create Role**

### Test that the user can switch to the role in the AWS console
Navigate to the **Roles** page.<br>
Click on the desired role from the list.<br>
In the **Summary** section, you'll find the link to switch roles. Click on the _copy_ icon.<br>
Open a new tab in your browser, and paste the copied link<br>
You should be directed a **Switch Role** page. The fields are automatically populated.<br>
Click **Switch Role**

Follow the same steps for the other 3 roles.