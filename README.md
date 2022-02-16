## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

![](https://github.com/munisshodmonov/Elk-Stack-Project1/blob/main/Diagram/Diagram-Project-Elk.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  [Filebeat-Playbook](https://github.com/munisshodmonov/Elk-Stack-Project1/blob/main/ansible/roles/filebeat-playbook.yml)
  [Metricbeat-Playbook](https://github.com/munisshodmonov/Elk-Stack-Project1/blob/main/ansible/roles/metricbeat-playbook.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting access to the network.
- _What aspect of security do load balancers protect? What is the advantage of a jump box?_
- Load Balancers protect from having DDoS attacks and ensure that servers dont become overloaded.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system statistics and metrics.
- _What does Filebeat watch for?_
- Filebeat watches for the information that is changed and show what time it took place.
- _What does Metricbeat record?_
- Metric records and logs services from the operating system that is running on the device. Then outputs them on Elasticsearch and Logstash.
- The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    | Server   | 10.0.0.5   | Linux            |
| Web-2    | Server   | 10.0.0.6   | Linux            |
| Elk-VM   | Server   | 10.1.0.4   | Linux            |
| Web-3    | Server   | 10.0.0.7   | Linux            |
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-Public IP - 98.169.37.147

Machines within the network can only be accessed by Jump-Box.
- _Which machine did you allow to access your ELK VM? What was its IP address?_
- Private IP - 10.0.0.4
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |   98.169.37.147      |
| Web-1    | No                  |   10.0.0.4           |
| Web-2    | No                  |   10.0.0.4           |
| Web-3    | No                  |   10.0.0.4           |
| Elk-VM   | Yes                 |   98.169.37.147      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- You are able to deploy multiple servers all at once just using one playbook
The playbook implements the following tasks:
- install Python-pip
- install Docker
- Install docker container
- Launch docker container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![](https://github.com/munisshodmonov/Elk-Stack-Project1/blob/main/Elk-Images/checkpoint-project11.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Public IP - 98.169.37.147

We have installed the following Beats on these machines:
- Private IP - 10.0.0.4 

These Beats allow us to collect the following information from each machine:
- Firebeat collects and logs data for each event that happened on the machine, meanwhile Metric beat analyzes metrics for the machine such as CPU and how much each service is using

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the install-elk.yml file to /etc/ansible/.
- Update the hosts file to include the new Elk-VM IP-address.
- Run the playbook, and navigate to http://[your.ELK-VM.External.IP]:5601/app/kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
