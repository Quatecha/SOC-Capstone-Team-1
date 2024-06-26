# Shuffle
In this documentation, you'll be installing Shuffle on Red Hat Enterprise Linux (RHEL).

NOTE: <br>
This guide has stopped just short of the required Docker Compose installation, as some dependencies between required RHEL yum updates and required Docker Compose dependencies were conflicting. This prevented the completion of this guide before the installation of Shuffle. Do not follow this guide unless you'd like to ONLY install Docker Engine on a RHEL instance.



## Vocabulary
* Webhook  -  a user-defined HTTP callback function that allows two APIs to communicate with each other in an event-driven way. Webhooks are triggered by an event in a web application and can send data and executable commands from one app to another over HTTP. Webhooks are automated, in other words, they are automatically sent out when their event is fired in the source system.
To recieve Webhook requests, you have to register for one or more of the events (aka topics) for which the platform offers a webhook. 
A webhook request will be sent to a destination endpoint on your application so you need to build one for it and register the URL as the *Webhook URL* for that event.




## Register for Red Hat 
Copy-paste the following link into your browser:<br>
`https://www.redhat.com/wapps/ugc/`

Complete the registration form and submit.<br>
Account Type:  `Personal`

Sign into the email account that you used in the RedHat registration. Open the recently sent e-mail, and click on the verification link to confirm and validate your new credentials. You will need these later.



# Create Shuffle-RedHat instance on AWS
Navigate to:<br>
`EC2  ->  Instances  ->  Launch instances`

Name:  `Shuffle-RedHat`<br>
AMI:  `Red Hat Enterprise Linux 9`<br>
Architecture:  `64-bit (x86)`<br>
Instance type:  `t2.micro`<br>
Key pair name:  `Shuffle-RedHat-key-pair`

**Network settings**<br>
VPC:  `SOC_VPC`<br>
Subnet:  `SOC_PrivSubnet`<br>
Auto-assign public IP:  `Enable`<br>
Create security group:  `<checked>`<br>
Security group name:  `Shuffle-RedHat-security-group`

**Configure storage**<br>
1x `10` GiB `gp3`

Click `Launch instance` button.


## Connect to Shuffle-RedHat instance
Open your host machine's terminal window.

Connect to the new instance using similar instructions from the [Metasploit](METASPLOIT#connect-to-ubuntu-instance.md) documentation.

Update Shuffle-RedHat instance with:<br>
`sudo yum update`

## Register with entitlement server
Register with the following command:<br>
`sudo subscription-manager register`

Enter the username and password you used to register on the Red Hat website.

<subscription-manager>

The output will display the user ID and the EC2 instance system name.<br>
Subscription Manager repositories is a collection of software packages that are specifically designed for subscribed RHEL systems.



# Docker

## Install Docker repository
First, you'll need to set up the Docker repository.

Install the **yum-utils** package:
```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

<install-docker-repo>



## Install Docker Engine
Install with the following command:<br>
`sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

<install-docker>

Confirm the install at the following prompt with:<br>
`y`

<confirm-docker-install>

When prompted for the GPG key, confirm that it matches the following key:<br>
`060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35`

...and accept with `y`

<confirm-docker-GPG-key>


## Start Docker
Start with the following command:<br>
`sudo systemctl start docker`

Verify proper Docker installation by accessing an image on Docker Hub:<br>
`sudo docker run hello-world`

<start-docker>


# Docker Compose
This makes managing your applications that implement Docker a little easier. 
You can just create one generic YAML file that will grab the specific containers and services that you need, and spin them up correctly so that they can communicate with each other.
You will be spinning up a few different containers, and those containers are taking advantage of services from other containers.

For example, the front-end and back-end will be taking advantage of an OpenSearch container that will be running the OpenSearch service within it. So it needs to be able to not only install OpenSearch and get that up and running, but it also needs to communicate with it.


## Install Docker Compose
IMPORTANT: 
Because of compatibility issues with some package dependencies (i.e. Python version conflicts) between the RHEL main updates and required dependencies installed along with Docker Compose, this guide will end here. 

In the future, I plan to continue this guide with a workaround after investigating which packages can be with-held during updates, so as to cause the least amount of conflicts and a working system.
