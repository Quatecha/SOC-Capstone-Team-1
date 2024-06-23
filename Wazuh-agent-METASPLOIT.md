# Installing Wazuh agent on Metasploit instance

You’ll be installing the Wazuh agent on the endpoint that you’ll want to monitor.<br>
It will send real-time data to the Wazuh server through an encrypted and authenticated channel.<br>
In this case, it’s the EC2 METASPLOIT Ubuntu instance.

Go into the AWS console, and start up the Metasploit instance.<br>
Once ready, connect to it via SSH or Instance Connect.<br>


## Add the Wazuh repository
This will need to be done with root permissions, so let’s temporarily grant root privileges to every command we enter.<br>
`$  sudo su`
<sudo-su>

Now we can install the GPG key:<br>
`$  curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg`

<add-gpg-key>

`curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH`  will download the Wazuh GPG key via cURL.<br>
`gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg`  will import the GPG key into the GnuPG keyring. <br>
* `--no-default-keyring`  tells the system not to use the default keyring.
* `--keyring gnupg-ring:`  specifies the keyring’s location at  `/usr/share/keyrings/wazuh.gpg`.
* `chmod 644 /usr/share/keyrings/wazuh.gpg`  changes the wazuh.gpg file permissions to give the owner read and write permissions. Everybody else will only have read permissions.

Check that the key was added properly with:<br>
`gpg --no-default-keyring --keyring /usr/share/keyrings/wazuh.gpg --list-keys`

<check-gpg-key>

Note that I'm sharing the public key here in the documentation. This isn't a huge deal because Public GPG keys and fingerprints are intended to be shared to allow others to verify signatures and encrypt messages.

Add the repository:<br>
`$  echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list`

<add-repository>

Update the package information:<br>
`$  apt-get update`

NOTE: if you see a message like so after running `apt-get update`, you might have accidentally installed the key twice. Check the troubleshooting section at bottom of this documentation to resolve.

<gpg-apt-update-warning>


## Deploy the Wazuh agent
Use the AWS Console to navigate to your EC2 WAZUH-manager instance Details page.<br>
Copy the  Public IPv4 address  to your clipboard.<br>

NOTE: Be sure to edit the WAZUH_MANAGER variable to contain your WAZUH-manager’s public IP that you just copied!<br>
`$  WAZUH_MANAGER=“<WAZUH-manager public IP>“ apt-get install wazuh-agent`

* `WAZUH_MANAGER=“<WAZUH-manager public IP>“`  -  this command sets the WAZUH_MANAGER environment variable to the manager’s IP address. This variable is used by the Wazuh agent to determine the Wazuh manager’s IP address or hostname. It can then send data to the manager using this variable. If the IP address or hostname of your manager ever changes, be certain to update it in the monitored endpoint’s environment variables as well.<br>
    * **Environment Variables**  are part of the environment in which processes run. These processes might be reliant upon these variables, so they access the variable when needed. These variables are commonly used to store configuration settings, system information, or paths to executables or libraries. It can be persistent or temporary. In this case, the Wazuh framework only uses it temporarily to define the manager’s IP address during installation, so that the Wazuh agent can communicate with the Wazuh server. 
    * If the manager weren’t on the same network, you might have to enter it’s public IP address instead. AWS might change the public IP address every time the instance is stopped and started again. If this is the case, you might be better off purchasing a dedicated address for your Wazuh endpoint instances.
* `apt-get  install  wazuh-agent`  -  this command installs the Wazuh agent package  `wazuh-agent`  on this endpoint. 


## Check proper Wazuh agent installation
You can use the following command to check that `wazuh-agent` has been installed in the **dpkg** database:<br>
`dpkg -l | grep wazuh-agent`

<check-dpkg>

Check that the Wazuh Manager's IP address has been added correctly in the following file with:<br>
`sudo nano /var/ossec/etc/ossec.conf`

You should notice the Wazuh Manager public IP address within the `<ossec-config>`  ->  `<client>`  ->  `<server>`  tags:

<ossec-config>


## Enable and start the Wazuh agent service
```
$  systemctl daemon-reload
$  systemctl enable wazuh-agent
$  systemctl start wazuh-agent
```
You’ve just enabled the systemd  `wazuh-agent`  service.

<start-wazuh-agent>


## Disable Wazuh updates
The Wazuh documentation recommends disabling updates.<br>
This is because compatibility between the Wazuh agent and Wazuh manager depends on the Wazuh manager version being later or equal to that of the agent.
```
$  sed -i "s/^deb/#deb/" /etc/apt/sources.list.d/wazuh.list
$  apt-get update
```

## Configure Security Group rules
The  **Security Group**  acts as the virtual firewall at the EC2 instance level.<br>
You'll need to allow traffic to and from your Wazuh agent.<br>
At the bottom of the EC2 instances window, click on the  **Security**  tab.<br>
`WAZUH-security-group`  ->  `Inbound rules`  ->  `Edit inbound rules`

Add two rules:<br>
Port range:  1514  |  Source: <Wazuh_manager_IP>  |  Description: For Wazuh agent<br>
Port range:  1515  |  Source: <Wazuh_manager_IP>  |  Description: For Wazuh agent

<Wazuh-Agent-security-groups>



## Configuration file
You can access the Wazuh configuration file at:<br>
`$  sudo nano /var/ossec/etc/ossec.conf`




# Troubleshooting

## 1. GPG key duplication
For various reasons that might cause complications in the system, you'll probably want to heed the warnings in the apt update output, and remove duplicates. 

If you accidentally duplicated the GPG key earlier, for example, you can simply check the file with:<br>
`nano /etc/apt/sources.list.d/wazuh.list`

<duplicate-gpg-keys-error>

<duplicate-gpg-keys-warning>

## 2. Wazuh Agent not connecting
* This might be due to a network security mechanism blocking a port. Check this EC2 instance's Security Group rules. It should have the Wazuh Manager's public IP address listed as source for ports 1514 and 1515. Also, the Wazuh manager's Security Group should allow for the Wazuh agent's public IP on ports 1514 and 1515.

* Otherwise, the Wazuh manager might not be listed in the Wazuh agent's configuration files. You can resolve this by accessing the config file with `sudo nano /var/ossec/etc/ossec.conf`. Be sure that instead of the agent's private IP address, that the _public IP_ is listed within the `<address>` tag, with no quotes. Then, restart the daemon.