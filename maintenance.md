# Connecting Wazuh Agent to Manager upon turning on instances

**Start instances**<br>
1. Navigate to EC2 Dashboard. 
2. Check the box for Wazuh-Manager and Metasploit-Ubuntu instances.
3. Click the `Start instance` button. 

![start-instances](./assets/maintenance-screenshots/start-instances.png)


**Update Wazuh Manager firewall rules**<br>
Each instance will now have a new public IP address which your firewalls will be blocking. Update the rules.

1. Navigate to the Metasploit-Ubuntu EC2 instance page. 
2. Copy the `Public IPv4 address` to your clipboard.

![copy-Metasploit-IP](./assets/maintenance-screenshots/copy-Metasploit-IP.png)

3. Navigate to Wazuh-Manager EC2 instance page.
4. Click on the `Security` tab.
5. Click on the `Wazuh-Manager-security-group` link.

![Wazuh-Manager-security-groups](./assets/maintenance-screenshots/Wazuh-Manager-security-groups.png)

6. Click on the `Edit inbound rules` button.

![manager-edit-inbound-rules](./assets/maintenance-screenshots/manager-edit-inbound-rules.png)

7. Paste the Metasploit-Ubuntu public IP address into the `1514` and `1515` rules. Remember that it needs the subnet’s CIDR.

![manager-rules-1514](./assets/maintenance-screenshots/manager-rules-1514.png)<br>
![manager-rules-1515](./assets/maintenance-screenshots/manager-rules-1515.png)

8. Click the `Save rules` button.


**Update Wazuh Agent firewall rules**<br>
Follow a similar protocol for the agent's firewall rules.

1. Navigate to the Wazuh-Manager EC2 instance page. 
2. Copy the `Public IPv4 address` to your clipboard.

3. Navigate to Metasploit-Ubuntu EC2 instance page.
4. Click on the `Security` tab.
5. Click on the `Metasploit-Ubuntu-security-group` link.
6. Click on the `Edit inbound rules` button.
7. Paste the Wazuh-Manager public IP address into the `1514` and `1515` rules. Remember that it needs the subnet’s CIDR.

8. Click the `Save rules` button.


**Update Wazuh Agent configuration file**<br>
This file can be accessed with the following command:<br>
`sudo nano /var/ossec/etc/ossec.conf`

Find the nested `<client> -> <server> -> <address>` tag near the top of the file.<br>
Paste the Wazuh manager's _public IP_ (instead of private IP) within the `<address>` tag, with no quotes.

![wazuh-agent-config](./assets/maintenance-screenshots/wazuh-agent-config.png)

Finally, restart the wazuh-agent daemon:<br>
`sudo systemctl restart wazuh-agent`

Check the service's status to make sure it's has started running recently (since restart):
`sudo systemctl status wazuh-agent`

![restart-agent-daemon](./assets/maintenance-screenshots/restart-agent-daemon.png)




# Resizing EC2 instance volume
I recommend that you intermittently check the available space in your instance before the storage completely runs out of space. You can view available storage with the following command:<br>
`df -h`

In the event that you'll need to extend storage space, the instructions can be found here:<br>
[EBS](EBS.md#modify-volume)

It is recommended that you first back up your instance with the following instructions:<br>
[EBS](EBS.md#create-volume-snapshot)

