# Installing Wazuh agent on Metasploit instance

You’ll be installing the Wazuh agent on the endpoint that you’ll want to monitor.<br>
It will send real-time data to the Wazuh server through an encrypted and authenticated channel.<br>
In this case, it’s the EC2 METASPLOIT Ubuntu instance.

Go into the AWS console, and start up the Metasploit instance.<br>
Once ready, connect to it via SSH or Instance Connect.<br>

## Add the Wazuh repository
This will need to be done with root permissions, so let’s temporarily grant root privileges to every command we enter.<br>
`$  sudo su`

Now we can install the GPG key:<br>
`$  curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg`

`curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH`  will download the Wazuh GPG key via cURL.<br>
`gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg`  will import the GPG key into the GnuPG keyring. <br>
* `--no-default-keyring`  tells the system not to use the default keyring.
* `--keyring gnupg-ring:`  specifies the keyring’s location at  `/usr/share/keyrings/wazuh.gpg`.
* `chmod 644 /usr/share/keyrings/wazuh.gpg`  changes the wazuh.gpg file permissions to give the owner read and write permissions. Everybody else will only have read permissions.

Add the repository:<br>
`$  echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list`

Update the package information:<br>
`$  apt-get update`

## Deploy the Wazuh agent
Use the AWS Console to navigate to your EC2 WAZUH-manager instance Details page.<br>
Copy the  Private IPv4 address  to your clipboard.<br>

NOTE: Be sure to edit the WAZUH_MANAGER variable to contain your WAZUH-manager’s private IP that you just copied!<br>
`$  WAZUH_MANAGER=“<WAZUH-manager private IP>“ apt-get install wazuh-agent`

* `WAZUH_MANAGER=“<WAZUH-manager private IP>“`  -  this command sets the WAZUH_MANAGER environment variable to the manager’s IP address. This variable is used by the Wazuh agent to determine the Wazuh manager’s IP address or hostname. It can then send data to the manager using this variable. If the IP address or hostname of your manager ever changes, be certain to update it in the monitored endpoint’s environment variables as well.<br>
    * **Environment Variables**  are part of the environment in which processes run. These processes might be reliant upon these variables, so they access the variable when needed. These variables are commonly used to store configuration settings, system information, or paths to executables or libraries. It can be persistent or temporary. In this case, the Wazuh framework only uses it temporarily to define the manager’s IP address during installation, so that the Wazuh agent can communicate with the Wazuh server. 
    * If the manager weren’t on the same network, you might have to enter it’s public IP address instead. AWS might change the public IP address every time the instance is stopped and started again. If this is the case, you might be better off purchasing a dedicated address for your Wazuh endpoint instances.
* `apt-get  install  wazuh-agent`  -  this command installs the Wazuh agent package  `wazuh-agent`  on this endpoint. 

## Enable and start the Wazuh agent service
```
$  systemctl daemon-reload
$  systemctl enable wazuh-agent
$  systemctl start wazuh-agent
```
You’ve just enabled the systemd  `wazuh-agent`  service.

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


## Configuration file
You can access the Wazuh configuration file at:<br>
`$  sudo nano /var/ossec/etc/ossec.conf`

