# Metasploit


### Create Ubuntu instance
Create an EC2 instance with the **Quick Start Ubuntu AMI**.

**Name:**  `Metasploit-Ubuntu`<br>
**Key pair name:**  `Metasploit-Ubuntu-key-pair`
<Metasploit-name>
<Metasploit-key-pair>

When you get to the **Network settings**, click the `Edit` button.<br>
Make sure you put it into the same VPC as the other instances.<br>
Create a new Security Group for it.

Create a new Subnet for the instance. This will be your vulnerable subnet. So good security practice is even more imperative.

### Network Settings
**VPC**:  `SOC-VPC`<br>
**Subnet**:  `defend-subnet`<br>
**Auto-assign public IP**:  `Enable`

### Security Group name:
**Metasploit-security-group**

### Inbound  Security Group Rules
**Type**:  `ssh`<br>
**Protocol**:  `TCP`<br>
**Port range**:  `22`<br>
**Source type**:  `Anywhere`

Give it the same Network logical containers as the [Kali](Kali.md) instance.<br>
Ex:
**VPC CIDR block**:  10.0.0.0/20
**Subnet name**:  `defend-subnet`
**Availability Zone**:  `US East (Ohio) / us-east-2a`
**IPv4 subnet CIDR block**:  `10.0.0.0/24`


You might not need much hard disk space, so you can leave at default 8GB EBS storage volume.<br>
**1x:  8 GiB  gp3**

Launch the instance.

You’ll be directed to the EC2  **Instances**  page.

### Connect to Ubuntu instance
Check the box for the  **Metasploit**  instance you’ve just created, and click on the  **Connect**  tab.

Click on the **copy to clipboard** icon next to the chmod command on number 3. This command will secure the key-pair file you downloaded earlier.<br>
Open your host machine’s terminal window.<br>
Navigate to the **Downloads** folder.<br>
Paste the command:<br>
`$  chmod 400 "Metasploit-Ubuntu-key-pair.pem"`

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


## Install Metasploit

The command to download and install Metasploit:
```
curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && \
  chmod 755 msfinstall && \
  ./msfinstall
```

Check for the new Metasploit file:<br>
`ls`

You should now see an `msfinstall` file.<br>
Check proper installation by executing the console for the Metasploit Framework:<br>
`msfconsole`

Congrats! You’ve just run Metasploit!!

To exit the Metasploit console, type:<br>
`exit`




<!-- Old Method to install Metasploit. Deprecated.

Now install some initial dependencies:<br>
`$  sudo apt install ruby ruby-dev build-essential zlib1g zlib1g-dev libpq-dev libpcap-dev libsqlite3-dev`

Clone the Metasploit github repository:
```
$  git clone https://github.com/rapid7/metasploit-framework.git
$  ls
```
You should now have a  **metasploit-framework**  directory in your current directory. Now change into that directory:<br>
`$  cd metasploit-framework`

Install Ruby’s bundler package manager:<br>
`$  sudo gem install bundler`

Finish installing the rest of the packages for Metasploit that are Ruby dependencies:
```
$  sudo bundle install
$  ls
```
-->