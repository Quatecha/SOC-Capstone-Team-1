# Connecting Wazuh Agent to Manager upon turning on

**Start instances**<br>
1. Navigate to EC2 Dashboard. 
2. Check the box for Wazuh-Manager and Metasploit-Ubuntu instances.
3. Click the `Start instance` button. 
<start-instances>


**Update Manager firewall rules**<br>
Each instance will now have a new public IP address which your firewalls will be blocking. Update the rules.

1. Navigate to the Metasploit-Ubuntu EC2 instance page. 
2. Copy the `Public IPv4 address` to your clipboard.
<copy-Metasploit-IP>
1. Navigate to Wazuh-Manager EC2 instance page.
2. Click on the `Security` tab.
3. Click on the `Wazuh-Manager-security-group` link.
<Wazuh-Manager-security-groups>
4. Click on the `Edit inbound rules` button.
<manager-edit-inbound-rules>
5. Paste the Metasploit-Ubuntu public IP address into the `1514` and `1515` rules. Remember that it needs the subnet’s CIDR.

<manager-rules-1514>
<manager-rules-1515>

6. Click the `Save rules` button.




# Resizing EC2 instance volume
