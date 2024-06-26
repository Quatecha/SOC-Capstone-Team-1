# Kali Linux

## Create EC2 instance
Navigate to the EC2 page in the AWS Services Console.

### Name and tags
**KALI-mr-rbt**

### Application and OS Images _(Amazon Machine Image)_<br>
Search **Kali** in the dashboard.<br>
Click the **AWS Marketplace AMIs** tab.<br>
The first result at top should be **Ver Kali Linux 2023.4**.<br>
Click on it, and click the **Subscribe Now** button on the following page.

### Instance type<br>
Back on the EC2 instance launch page, the minimum requirement for this Kali AMI is a:<br>
**Instance Type:  t2.medium**

Each EC2 instance using the instance type incurs a charge of:<br>
**$0.046/Hr**

This instance type is not eligible for our AWS free tier, but that’s the way the cookie crumbles.

After choosing the minumum Instance type, scroll down to **Key pair (login)**.<br>
### Create new key pair<br>
**Key pair name:  KALI-mr-rbt-KEY-PAIR**<br>
**Key pair type:  RSA**<br>
**Private key file format:  .pem**

Click **Create key pair** button.<br>
This will create and download your key pair, which you’ll find in the **Downloads** folder by default if using Chrome browser.

### Network Settings
**VPC:  SOC-VPC**<br>
**Subnet:  attack-subnet**<br>
**Auto-assign public IP:  Enable**<br>

### Security Group name:
**Kali Linux-Kali Linux 2023.4-AutogenByAWSMP--2**

### Inbound  Security Group Rules
**Type:  ssh**<br>
**Protocol:  TCP**<br>
**Port range:  22**<br>
**Source type:  Anywhere**

### Configure Storage
The AWS free tier allows up to 30 GB of **General Purpose SSD** or **Magnetic** storage. The default is **12 GB gp2**, so you can take advantage and manually change the size and throughput quality of volume!<br>
But for now you might not need it. Provisioning extra hard disk space will use the allotted Free Tier storage, so let's stick to the default of 8GB.
**1x:  8 GiB  gp3**



## Connect to Kali instance
Check the box for the KALI instance you’ve just created, and click on the **Connect** tab.

Click on the **copy to clipboard** icon next to the chmod command on number 3. This command will secure the key-pair file you downloaded earlier.<br>
Open your host machine’s terminal window.<br>
Navigate to the **Downloads** folder.<br>
Paste the command:<br>
`$  chmod 400 "KALI-mr-rbt-KEY-PAIR.pem"`

This command has secured the key-pair file you downloaded earlier to only provide read permissions to root user, and restricts any other user of any permissions.

Go back to the **Connect to instance** page, and copy the ssh command in the provided **Example** at bottom of page.<br>
Paste it into your host machine’s terminal.<br>
`$  ssh -i "KALI-mr-rbt-KEY-PAIR.pem" root@203.0.113.5`

When prompted with:<br>
`Are you sure you want to continue connecting (yes/no/[fingerprint])?`
...type yes:<br>
`$  yes`

You should see the message:<br>
`Warning: Permanently added '203.0.113.5' (ED25519) to the list of known hosts.`

You’ve just added the public key to your system’s list of known hosts. Whenever you connect to this EC2 instance, the server will present it’s SSH key, and your host system will check in the `known_hosts` file for a matching key. If it matches, it is safe and you can connect.

You should now be connected to the Kali instance!

## Update Kali instance
Run:<br>
```
$  sudo apt update
$  sudo apt upgrade
```
...to update the debian dependencies.
