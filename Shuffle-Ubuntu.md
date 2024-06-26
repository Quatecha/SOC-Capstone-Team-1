# Shuffle
In this documentation, you'll be installing Shuffle on Red Hat Enterprise Linux (RHEL).



## Vocabulary
* Webhook  -  a user-defined HTTP callback function that allows two APIs to communicate with each other in an event-driven way. Webhooks are triggered by an event in a web application and can send data and executable commands from one app to another over HTTP. Webhooks are automated, in other words, they are automatically sent out when their event is fired in the source system.
To recieve Webhook requests, you have to register for one or more of the events (aka topics) for which the platform offers a webhook. 
A webhook request will be sent to a destination endpoint on your application so you need to build one for it and register the URL as the *Webhook URL* for that event.




# Create Ubuntu instance
Iin order to 

Create an EC2 instance with the **Quick Start Ubuntu AMI**.

**Name:**  `Shuffle-Ubuntu`<br>
**Key pair name:**  `Shuffle-Ubuntu-key-pair`

When you get to the **Network settings**, click the `Edit` button.<br>
Make sure you put it into the same VPC as the other instances.<br>
Create a new Security Group for it.


### Network Settings
**VPC**:  `SOC-VPC`<br>
**Subnet**:  `SOC_PubSubnet2`<br>
**Auto-assign public IP**:  `Enable`

### Security Group name:
**Shuffle-Ubuntu-security-group**

### Inbound  Security Group Rules
**Type**:  `ssh`<br>
**Protocol**:  `TCP`<br>
**Port range**:  `22`<br>
**Source type**:  `Anywhere`


You might not need much hard disk space, so you can leave at default 8GB EBS storage volume.<br>
**1x:  8 GiB  gp2**

Launch the instance.

You’ll be directed to the EC2  **Instances**  page.

### Connect to Ubuntu instance
Check the box for the  **Metasploit**  instance you’ve just created, and click on the  **Connect**  tab.

Click on the **copy to clipboard** icon next to the chmod command on number 3. This command will secure the key-pair file you downloaded earlier.<br>
Open your host machine’s terminal window.<br>
Navigate to the **Downloads** folder.<br>
Paste the command:<br>
`$  chmod 400 "Shuffle-Ubuntu-key-pair.pem"`

This command has secured the key-pair file you downloaded earlier to only provide read permissions to root user, and restricts any other user of any permissions.

Go back to the  **Connect to instance**  page, and copy the ssh command in the provided  **Example**  at bottom of page.<br>
Paste it into your host machine’s terminal.

When prompted with:<br>
`Are you sure you want to continue connecting (yes/no/[fingerprint])?`<br>
...type yes:<br>
`$  yes`

You should see the message:<br>
`Warning: Permanently added '203.0.113.5' (ED25519) to the list of known hosts.`

You’ve just added the public key to your system’s list of known hosts. Whenever you connect to this EC2 instance, the server will present it’s SSH key, and your host system will check in the  `known_hosts`  file for a matching key. If it matches, it is safe and you can connect.

You should now be connected to the Ubuntu Metasploit instance!

### Update Ubuntu instance
Run:<br>
```
$  sudo apt update
$  sudo apt upgrade
```
...to update the debian dependencies.



# Install Docker Engine and Docker Compose
This installation is for your Ubuntu server instance, with no graphical interface.<br>
Installation instructions can be found at:<br>
[Docker](Docker.md)












<!-- 
Continue video at Docker Compose installation, in case any configurations have to be done
-->