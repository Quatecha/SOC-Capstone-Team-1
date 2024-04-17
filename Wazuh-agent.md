# Wazuh manager installation with Amazon Linux using RDP


## Create Amazon Linux EC2 instance
**Name:**  _WAZUH-manager_
**Key pair name:**  _WAZUH-manager-KEY-PAIR_

Search for MATE in the AMI search bar.<br>
Choose the free tier elegible “Amazon Linux 2 with .NET 6, PowerShell, Mono, and MATE Desktop Environment” AMI.<br>
Give it the same options as the METASPLOIT instance.

However, you’ll want to create a  _WAZUH-manager-security-group_.<br>
It will only accept SSH traffic.

We will also plan on connecting via RDP (Remote Desktop Protocol).<br>
So add a new rule.<br>
**Type:**  _RDP_
**Source:**  _My IP_

Keep the default SSH rule with the source listed as  `0.0.0.0/0`  which means from  `Anywhere`, and it is still considered quite safe.This is because the connection requires the  _.pem_  security key pair, which is encrypted with the RSA algorithm. 

Launch the instance.<br>
You’ll be directed to the EC2 Instances page.


### Configure Security Group rules
The  **Security Group**  acts as the virtual firewall at the EC2 instance level.<br>
You'll need to allow traffic to and from your Wazuh agent.<br>
At the bottom of the EC2 instances window, click on the  **Security**  tab.<br>
`WAZUH-security-group`  ->  `Inbound rules`  ->  `Edit inbound rules`

Add two rules:<br>
Port range:  1514  |  Source: <Wazuh_agent_IP>  |  Description: For Wazuh agent<br>
Port range:  1515  |  Source: <Wazuh_agent_IP>  |  Description: For Wazuh agent


### Connect to Amazon Linux 2 AMI instance
You already know how to connect via SSH. So let’s try a new connection.<br>
After the instance is up and running, click on the  ‘_EC2 Instance Connect_’ tab.

Change the username from  `root`  to  `ec2-user`. This is the default user for any EC2 instance. Additionally, it’s the only user that the Amazon Linux AMI accepts.<br>
Click on  _Connect_.

A new browser window will launch, and you’ll conveniently be securely connected to your Linux instance.<br>
This tool is built into EC2 instances, and can be accessed from the AWS console.<br>
How easy was that?!

Now let’s update the packages.<br>
Instead of using  `apt-get`  like you might be used to, this Amazon Linux distribution uses the  `yum`  package manager. YUM (Yellow Dog Updater, Modified) is an open-source Linux package management application that uses the RPM package manager. It allows you to search official and third-party repositories and install, update, or remove packages from the system.<br>
`$  sudo yum update -y`

After the updates have finished downloading and installing, update the password for the current user  `ec2-user`  that you switched to earlier.<br>
`$  sudo passwd ec2-user`

Type in your new password. Then confirm the new password.<br>
Try to use a secure password, since you might end up opening ports on the instance later on down the line and opening the attack surface.<br>
If you forget it, you can log back in as root and change the password.<br>
The password that you’ll absolutely always want to remember is the root user’s password. If you forget this password, you will not be able to change it.<br>
AWS configures the EC2 instances to not be able to change the password on the root account. Enabling the root password is a process with many steps. Stay tuned for a guide that I’ll be writing on it.

Now download the Microsoft Remote Desktop Protocol application. Amazon Linux 2 supports using Microsoft RDP to connect to your instance from your host.<br>
You can find the link at this url for the Apple Store:<br>
`https://apps.apple.com/us/app/microsoft-remote-desktop`

After it’s downloaded and installed, open the application.<br>
Click  _Add PC_.<br>
Click  _User account_  ->  _Add User Account_<br>

Copy the credentials from your WAZUH instance into the application:<br>
**PC name:**  _203.0.113.5_<br>
**User Name:**  _ec2-user_<br>
**Password:**  _<passwd you previously entered>_<br>
**Friendly Name:**  _Wazuh User_<br>

Click _Add_<br>
You’ll see the new connection in the window.<br>
Double click.<br>
_Continue_ with the connection, since it’s our trusted instance.

If you do not have access, you might need to reboot your instance.

You should now see the MATE GUI for your WAZUH instance! Congrats!


## Install Wazuh Manager
This method uses the Wazuh installation assistant. Note that the Wazuh Indexer is not compatible for installation on an m1 chip, making the long manual installation of the Wazuh Server and Wazuh Dashboard pointless. Wazuh should not be installed on a Mac silicon chip, as does not fully support the ARM architecture.

First, let’s scale our EC2 instance to  _t2.medium_. The current instance type for the EC2 instance isn’t supported by the automatic wizard installation.<br>
Our current free tier  _t2.micro_  instance type only has 1 core and 1 GB of RAM.<br>
The minimum requirements are 2 core CPU, and 4GB of RAM. 

### Vertically scale EC2 instance
1. Stop instance
2. Refresh page
3. Actions  ->  Instance Settings  ->  Change instance type

**New instance type:**  _t2.medium_<br>
**Memory:**  _4GB_<br>
**vCPUs:**  _2_

Start the instance.


### Install Wazuh using automatic installation assistant
Download Wazuh installation assistant, and install Wazuh server:<br>
`$  curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash ./wazuh-install.sh -a`

This command executing the following tasks:<br>
`$  curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh`
* This command is using  **cURL**  which uses the  `https://packages.wazuh.com/4.7/`  url to download the  `wazuh-installation.sh`  script.
* `-s`  flag operates cURL in silent mode. It won’t clutter the terminal screen by show progress or error messages.
* `-O`  flag tells cURL to save the downloaded file with the same name as the remote file.

The second part of the command is connected by the  `&&`  logical operator to to execute the second command if the first command executes successfully:<br>
`$  sudo bash ./wazuh-install.sh -a`<br>
* `sudo bash ./wazuh-install.sh`  uses  `bash`  to execute the downloaded shell script  `./wazuh-install.sh` with sudo privileges.

This will install the following items:<br>
* **Wazuh Indexer**
* **Wazuh server**
* **Filebeat**
* **Wazuh Dashboard**

It will also initialize the Wazuh Dashboard web application.

Wazuh is installed and configured. This saves us the time involved to do it manually.<br>
At some point in the future, I’ll include the documentation for the manual installation.<br>

The installation process has automatically created a few files in your system.<br>
Among them is the passwords file for the different Wazuh components and other technology dependencies needed to operate.<br>
This includes users and passwords for the Dashboard, Web User Interface, Indexer, Filebeat, Wazuh API, etc.<br>
You can access it with the following command:<br>
`$  sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt`

Here are the access credentials for remote browser access to dashboard.<br>
**Wazuh Dashboard web interface:**  _https://<wazuh_dashboard_ip>:443_<br>
**User:**  _admin_<br>
**Password:**  _<randomly_generated_password>_<br>

Before you try to access it, you’ll need to allow the EC2 instance to accept HTTPS traffic.<br>
WAZUH-security-group  ->  Inbound rules  ->  Edit inbound rules<br>
**Type:**  _HTTPS_<br>
**Source:**  _My IP_<br>
**Description:**  _For Wazuh Dashboard_<br>

You can now access Wazuh Dashboard from your host machine’s browser.<br>
Use the login credentials shown from the  `wazuh-passwords.txt`  file.<br>

Congrats! You’ve just accessed the Wazuh Dashboard being hosted on your EC2 instance.

You can now begin deploying agents.


## Configuration files
Access the Wazuh configuration file at:<br>
`$  sudo nano /var/ossec/etc/ossec.conf`

Access the Filebeat configuration file at:<br>
`$  sudo nano /etc/filebeat/filebeat.yml`

Access the Wazuh passwords file at:<br>
`$  sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt`