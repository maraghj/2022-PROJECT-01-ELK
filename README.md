# 2022-PROJECT-01-ELK-STACK
Cybersecurity Bootcamp Project 1: Cumulative Networking, Cloud Security, ELK Stack product

## Automated ELK Stack Deployment

![alt text](https://github.com/maraghj/2022-PROJECT-01-ELK/blob/main/ELK_DIAGRAM.JPG?raw=true)

The files in this repository were used to configure the network depicted below.

Elk-stack-Diagram: ELK_diagram.png These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat. -filebeat-playbook.yml -metricbeat-playbook.yml This document contains the following details:

Description of the Topology

Access Policies

ELK Configuration

Beats in Use

Machines Being Monitored

How to Use the Ansible Build

Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application. Load balancing ensures that the application will be highly available in addition to restricting access to the network. -Load balancers distribute traffic to servers to prevent any one server from being overloaded. This protects against DDoS attacks by preventing servers from being overloaded. The jump box has the advantages of allowing access to the user froma single node, and this means it can be more easily secured and monitored. Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs. -Filebeat will monitor log files, collect those events and forward them to the ELK stack. -Metricbeat periodically records metric data, including operating system metrics like CPU or memory data related to the services running on the servers.

The configuration details of each machine may be found below.

|Name		|Function	|IP Address	|Operating System |
|---------------|---------------|---------------|-----------------|
|Jump Box	|Gateway	|10.0.1.4	|Ubuntu 18.04     |
|VM 1		|DVWA		|10.0.1.6	|Ubuntu 18.04     |
|VM 2		|DVWA		|10.0.1.7	|Ubuntu 18.04     |
|ELK		|Server		|10.1.0.4	|Ubuntu 18.04     |

## Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the jump box provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

-Personal IP address

Machines within the network can only be accessed by the Jump Box. The Elk Machine can have access from personal IP address through port 5601.

A summary of the access policies in place can be found in the table below.

|Name		|Publicly Accessible		|Allowed IP Addresses|
|---------------|-------------------------------|--------------------|
|Jump Box	|Yes				|Personal            |
|Load Balancer	|Yes				|Open                |
|Web 1		|No				|10.0.1.6            |
|Web 2		|No				|10.0.1.7            |
|ELK Server	|Yes				|Personal            |

