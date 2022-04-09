# 2022-PROJECT-01-ELK-STACK
Cybersecurity Bootcamp Project 1: Cumulative Networking, Cloud Security, ELK Stack product

## Automated ELK Stack Deployment

![alt text](https://github.com/maraghj/2022-PROJECT-01-ELK/blob/main/diagrams/ELK_DIAGRAM.JPG)

The files in this repository were used to configure the network depicted below.

Elk-stack-Diagram: ELK_diagram.png These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat. -filebeat-playbook.yml -metricbeat-playbook.yml This document contains the following details:

Description of the Topology

Access Policies

ELK Configuration

Beats in Use

Machines Being Monitored

How to Use the Ansible Build

Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application. 

Load balancing ensures that the application will be highly available in addition to restricting access to the network. 

Load balancers distribute traffic to servers to prevent any one server from being overloaded. This protects against DDoS attacks by preventing servers from being overloaded. 

The jump box has the advantages of allowing access to the user froma single node, and this means it can be more easily secured and monitored. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs. -

-Filebeat will monitor log files, collect those events and forward them to the ELK stack. 

-Metricbeat periodically records metric data, including operating system metrics like CPU or memory data related to the services running on the servers.

The configuration details of each machine may be found below.

|Name		|Function	|IP Address	|Operating System |
|---------------|---------------|---------------|-----------------|
|Jump Box	|Gateway	|10.0.1.4	|Ubuntu 18.04     |
|VM 1		|DVWA		|10.0.1.6	|Ubuntu 18.04     |
|VM 2		|DVWA		|10.0.1.7	|Ubuntu 18.04     |
|ELK		|Server		|10.1.0.4	|Ubuntu 18.04     |

## Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Ansible jumpbox machine can accept connections fron the internet

Access to this machine can only be allowed from personal ip address

The ELK is accessed from the jumpbox and not directly from the personal ip address

A summary of the access policies in place can be found in the table below.

|Name		|Publicly Accessible		|Allowed IP Addresses|
|---------------|-------------------------------|--------------------|
|Jump Box	|Yes				|Personal            |
|Load Balancer	|Yes				|Open                |
|Web 1		|No				|10.0.1.6            |
|Web 2		|No				|10.0.1.7            |
|ELK Server	|No				|JBOX                |

## ELK Configuration

Ansible was used to automate Ansible was used to automate configuration of the ELK machine. 

No configuration was performed manually, which is advantageous because the automation is is less vulnerable to human error and more efficient, scalable and repeatable. 

The playbook implements the following tasks;


## Target Machines

The ELK is configured to mornitor the following machines

- 10.0.1.6
- 10.0.1.7

Beats have been installed on both machines where as Filebeact collects webserver logs and any system file changes.

While the Metricbeat monitors for the operating system which includes the CPU and Memory 

## Using the Playbook

In order to use the playbook you will need to have ANsible control all ready configured.

To get to your Ansible you will need to ssh to your jbox once in the jbox you will do the following to vewrify your Ansible

1. sudo docker container list -a which will show your ansible container

2. access the container you will now sudo docker container start, 

3. now you can either reference the container name or the container id and sudo docker container attach 

4. now once attached you will now cd into the Ansible using cd /etc/ansible

Now that you are finally in the ansible you can run your playbooks using ansible-playbook filebeat-playbook.yml and ansible-playbook metricbeat-playbook.yml

Once installed you can now go to Kibana using your ELK ip xx.xx.xxx.xxx:5601 to verify both metric are working as required.
