## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

# Network Diagram
![alt text](https://github.com/Suleadigun/ELK-Project1/blob/main/Diagrams/Sule%20-%20Cloud%20Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

## My Playbook(s)
[Filebeat Playbook](https://github.com/Suleadigun/ELK-Project1/blob/main/Ansible/files/filebeat-config.yml)

[Metricbeat Playbook](https://github.com/Suleadigun/ELK-Project1/blob/main/Ansible/roles/metricbeat-playbook.yml)
 
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

Load balancers are used to add additional layers of security like WAFs, authentication, DDoS. The advantage of a jump box create a secure middle connection that admins connect to first before connecting to a network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.

- Filebeat is used to monitors log files and locations
- Metricbeat records metrics or statistics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function   | IP Address | Operating System |
|------------|------------|------------|------------------|
| Jumpbox    | Gateway    | 10.0.0.4   | Linux            |
| ELK Server | ELK Stack  | 10.1.0.4   | Linux            |
| Web 1      | Web Server | 10.0.0.5   | Linux            |
| Web 2      | Web Server | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
**24.240.91.251, 73.164.22.156, 73.164.102.46**

Machines within the network can only be accessed by Jumpbox.
Jumpbox is allowed to connect, IP Address is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Main advantages are that it saves time, reduces errors or bugs that may be found in script before deployment, also verifies that any system deployed to is configured the same.

The playbook implements the following tasks:

-Install Docker.io
- Install Pip3/Python
- Download and launch ELK Docker Container
- Enable Docker Service on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6

We have installed the following Beats on these machines:
-Filebeat & Metricbeat

These Beats allow us to collect the following information from each machine:

- Filebeat is used to monitors log files and locations
- Metricbeat records metrics or statistics

We would probably see authentication requests, metrics like CPU usuage.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the host file to /etc/ansible.
- Update the host file to include webservers
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? The playbooks end in .yml and should be copied to /etc/ansible/playbooks
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? - Edit the host file
- _Which URL do you navigate to in order to check that the ELK server is running? - your-ip:5601/app/kibana#/home?_g=0

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
