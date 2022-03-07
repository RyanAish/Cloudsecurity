# Cloudsecuriy
Unit 13 Elk Stack Project

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Cloud Security.drawio.png](https://github.com/RyanAish/Cloudsecuriy/blob/5292560eb0e2a9db4421c0232cbfd3083d0ebc79/Diagrams/Cloud%20Security.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

  - [Filebeat-playbook.yml](https://github.com/RyanAish/Cloudsecurity/blob/7c06aa735a9e6023b397dd47477002a3997cfb6a/Anisble/filebeat-playbook.yml)
  - [Metric-playbook.yml](https://github.com/RyanAish/Cloudsecurity/blob/7c06aa735a9e6023b397dd47477002a3997cfb6a/Anisble/metricbeat-playbook.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will have avalibitiy for clients, in addition to restricting attacks to the network. Therefore, if a server goes down or needs to be patched, the other server would be able to handle the traffic. Jump box are gateway access to an infrastructure that reducing the potential of an attack, via SSH which uses port 22.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | Public:52.170.16.95 Private:10.0.0.4   | Linux    |
| WEB-1    | Server   | Public: N/A Private:10.0.0.5   | Linux            |
| WEB-2    | Server   | Public: N/A Private:10.0.0.6   | Linux            |
| WEB-3    | Server   | Public: N/A Private:10.0.0.8   | Linux            |
| ELK-STACK|Monitoring| Public:52.190.184.126 Private:10.1.0.4 | Linux    |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- The JumpBox machine was accessed by my network with the following IP address, for security purposes this is a randomly generated IP: 

Machines within the network can only be accessed by Jump-Box-Provisioner.
Only my home computer was allowed access to the ELK-Server. 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 67.195.792.247       |
| WEB-1    | No                  | 10.0.0.4             |
| WEB-2    | No                  | 10.0.0.4             |
| WEB-3    | No                  | 10.0.0.4             |
| ELK-STACK| No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it's simplitic in itself, and prevents any overlook vulnerabilites. No special coding is required, Ansible is flexible and lets you model even the higly complex workflows.

The playbook implements the following tasks:

* Install docker.io
* Install python3-pip
* Install docker
* Increase vitrual memory



The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Docker.png](https://github.com/RyanAish/Cloudsecurity/blob/3f2bb624405fff5d218f8493fcfbfbbd33470cc0/Images/Docker%20copy.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:

| Name     | IP Address|
|----------|----------|
| WEB-1    | 10.0.0.5 |
| WEB-2    | 10.0.0.6 |
| WEB-3    | 10.0.0.8 |


We have installed the following Beats on these machines:
* Filebeat
* Metricbeat

| Name     | IP Address|
|----------|----------|
| WEB-1    | 10.0.0.5 |
| WEB-2    | 10.0.0.6 |
| WEB-3    | 10.0.0.8 |
| ELK-STACK| 10.1.0.4 |


These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to Ansible directory.
- Update the Host file to include  
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ I copied that playboks to the roles directories.
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running? ( http://[your.VM.IP]:5601/app/kibana )

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
