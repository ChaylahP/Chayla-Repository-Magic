## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Azure Map](https://github.com/ChaylahP/Chayla-Repository-Magic/blob/main/13-ELK%20Project/Diagrams/Azure%20Diagram.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAMLfile may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: elk_playbook.yml
  
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly EFFECTIVE, in addition to restricting TRAFFIC ACCESS to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
- Load Balancers prevent unwanted or unauthorized traffic from reaching the application. 
- Jumpbox adds security layer to the web servers preventing them from being exposed to the public.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the CONFIGURATION FILES and system FILES.
- _TODO: What does Filebeat watch for? Filebeats watch for log files or log event.
- _TODO: What does Metricbeat record? Metricbeat records metrics from on going services on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.2.0.4   | Linux            |
| Web01    |Webserver   10.2.0.5   | Linux            |                  
| Web-02   |Webserver   10.2.0.6   | Linux            |                  
| Web03    |Webserver   10.5.0.4   | Linux            |                  

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JUMPBOX machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 20.53.198.188

Machines within the network can only be accessed by JUMPBOX.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?
- Allowed access to my personal computer with IP Addresses of 20.53.198.188

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes              | 10.0.0.1 10.0.0.2    
| Web01    | No               | 20.53.198.188                    
| Web-02   | No               | 20.53.198.188
| Web03ELK   Yes                13.78.44.63


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?
- It is flexible because it allows changes to be made within any of the virtual machines associated with it.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- 1.Install Docker.io
- 2. Install Python3-pip
- 3. Install Docker Python Module 
- 4. Download and launch a Docker web container 
- 5. Download and launch a Docker web container 
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output]

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring
10.2.0.4, 10.2.0.5, 10.2.0.6, 10.5.0.4

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
- Filebeat and Metricbeat 

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
- Filebeat monitors log files and log events. Example: Inputs as well as harvesters. Mectribeats looks out for any information in the file system which has been manipulated.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ANSIBLE CONFIGURATION file to RUN PLAYBOOKS.
- Update the ANSIBLE HOST file to include...
- Run the playbook, and navigate to JUMPBOX to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? 
- Elk-Plyabook.yml 
- 
-  Where do you copy it?
-  Ansible 
-  
- _Which file do you update to make Ansible run the playbook on a specific machine? 
- Elk-Playbook.yml file 
- 
- How do I specify which machine to install the ELK server on versus which to install Filebeat on?
- Using the IPs to the respective servers 

- _Which URL do you navigate to in order to check that the ELK server is running?
- http://[Elkproject1vm-ip]:5601/app/kibana 

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.
- ansible-playbook elk-playbook.yml
