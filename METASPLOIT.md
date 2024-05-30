# Metasploit

### Create Ubuntu instance
**Name:**  `METASPLOIT-ubuntu`<br>
**Key pair name:**  `METASPLOIT-ubuntu-KEY-PAIR`

Create an EC2 instance with the **Quick Start Ubuntu AMI**.

Give it the same options as the KALI instance.<br>
You might not need much hard disk space, so you can leave at default 8GB EBS storage volume.<br>
**1x:  8 GiB  gp3**

Launch the instance.

You’ll be directed to the EC2  **Instances**  page.

### Connect to Ubuntu instance
Check the box for the  **METASPLOIT**  instance you’ve just created, and click on the  **Connect**  tab.

Click on the **copy to clipboard** icon next to the chmod command on number 3. This command will secure the key-pair file you downloaded earlier.<br>
Open your host machine’s terminal window.<br>
Navigate to the **Downloads** folder.<br>
Paste the command:<br>
`$  chmod 400 "METASPLOIT-ubuntu-KEY-PAIR.pem"`

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

You should now be connected to the Ubuntu METASPLOIT instance!

### Update Ubuntu instance
Run:<br>
```
$  sudo apt update
$  sudo apt upgrade
```
...to update the debian dependencies.

## Install Metasploit
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
You should now see an abundant list of directories and files.<br>
Check proper installation by executing the console for the Metasploit Framework:<br>
`$  ./msfconsole`

Congrats! You’ve just run Metasploit!!
