# Ansible-MOTD
Enhance server logins with a customizable Ansible MOTD script. Admins easily manage dynamic welcome messages, sharing server status, maintenance notices, updates, and more.

This Ansible MOTD (Message of the Day) script is designed to enhance server login experiences by providing a customizable and dynamic welcome message for users. It allows system administrators to easily configure and manage the content displayed to users upon login, providing valuable information such as server status, maintenance notices, important updates, or any other relevant details.
<div>
  <img src="https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white" />
</div>
<div>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
</div>
<div>
  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" />
</div>

## ✅ Key Features:

- Dynamic Message: The script enables the generation of dynamic messages by incorporating various system-related variables, including hostname, IP address, current date and time, system load, and more.
- Customization: Administrators can easily customize the MOTD content according to their specific needs and preferences by modifying the script's variables and templates.
- Maintenance Mode: During system maintenance or planned downtime, administrators can activate a maintenance mode to display specific messages to users, notifying them about the ongoing work and expected downtime.
- Version Control: By leveraging Ansible, the script ensures consistent deployment and version control across multiple servers, making it convenient for managing MOTD configurations in large-scale environments.


## 📦 Getting Started:
- Clone the Ansible MOTD Script repository.
- Customize the MOTD message template and variables to fit your requirements.
- Execute the Ansible playbook to deploy the updated MOTD configurations to your target servers.
- Enjoy an enhanced login experience for your users with personalized and dynamic messages!
- Or if you're a tinkerer, use the following to steps to create your own file path and MOTD

### Step 1:
Create a directory for your Ansible Playbooks
```
sudo mkdir /Path/To/File/Ansible/MOTD
```
Change directories into your MOTD folder
```
cd /Path/To/File/Ansible/MOTD
```
### Step 2:
Using the command below, we will setup our roles folder needed for the MOTD:
```
sudo ansible-galaxy init /Path/To/File/roles/motd
```
### Step 3:
Change directories into the roles folder you just created:
```
cd /Path/To/File/roles/motd
```
in the MOTD directory, create a new directory called templates
```
sudo mkdir templates
```
### Step 4:
Within the templates folder, create a jinja file called 96-access-warning.j2
```
sudo nano 96-access-warning.j2
```
Inside the Jinja template, paste the following:
```
#!/bin/sh
echo
echo "
  ____  _____ ______     _______ ____    _   _    _    __  __ _____ 
 / ___|| ____|  _ \ \   / / ____|  _ \  | \ | |  / \  |  \/  | ____|
 \___ \|  _| | |_) \ \ / /|  _| | |_) | |  \| | / _ \ | |\/| |  _|  
  ___) | |___|  _ < \ V / | |___|  _ <  | |\  |/ ___ \| |  | | |___ 
 |____/|_____|_| \_\ \_/  |_____|_| \_\ |_| \_/_/   \_\_|  |_|_____|
                                                                    
#############################################################################################################################################
ALERT! You are entering into a secured area! Your IP, Login Time, Username has been noted and has been sent to the server administrator!
This service is restricted to authorized users only. All activities on this system are logged. Unauthorized access will be fully investigated
and reported to the appropriate law enforcement agencies.You are accessing Your Company Name Property. Go away if you have no business
being here. If you believe this message was generated in error, please contact: YOURINFO@COMPANY.COM
#############################################################################################################################################
"

echo "
================================================================
"
echo "Your Public IP address is: "
echo
curl -s http://whatismyip.akamai.com/
echo
echo "
================================================================
"
```


With the Ansible MOTD Script, you can streamline server administration, improve communication with users, and provide essential information in a concise and visually appealing manner. Enhance your server's welcome message and make your users feel more informed and engaged upon login.

**Note: This script is intended for use with servers running Ansible and can be easily integrated into existing Ansible playbooks or deployment workflows.**
