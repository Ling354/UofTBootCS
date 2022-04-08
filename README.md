## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Red-Team Network Diagram](https://github.com/Ling354/UofTBootCS/blob/62776268207472a4a92e74177bee128db647840b/Diagrams/Red-Team%20Network%20Diagram.png)


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat.

[install-elk.yml](Ansible/install-elk.yml) --hit

[filebeat-config.yml](Ansible/filebeat-config.yml) --hit

[metricbeat-config.yml](Ansible/metricbeat-config.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly accessable, in addition to restricting in bound traffic to the network.

Load balancers are able to protect against DDoS attacks by moving traffic to different servers.  The advantage of using a jump box is allowing admins to first connect to this node to allow secure access to other servers.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system metrics.
Filebeat observes log file data. This can include audit logs, server logs and others.
Metricbeat records machine metrics like uptime.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name          | Function      | IP Address | Operating System |
|---------------|---------------|------------|------------------|
| Jump Box      | Gateway       | 10.1.0.4   | Linux (Ubuntu)   |
| Web-1         | Webserver     | 10.1.0.5   | Linux (Ubuntu)   |
| Web-2         | Webserver     | 10.1.0.6   | Linux (Ubuntu)   |
| elk-server    | Monitor       | 10.0.0.4   | Linux (Ubuntu)   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

my personal IP

Machines within the network can only be accessed by Jump Box Provisioner.

My Personal IP port 5601

A summary of the access policies in place can be found in the table below.

| Name       | Publicly Accessible | Allowed IP Addresses |
|------------|---------------------|----------------------|
| Jump Box   | Yes                 | Personal IP          |
| Web-1      | No                  | 10.1.0.4             |
| Web-2      | No                  | 10.1.0.4             |
| elk-server | No                  | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because Ansible is free and open source, it is efficient and powerful.

The playbook implements the following tasks:
- Install Docker
- Install Python3-pip
- Install Docker Module
- Increase virtual memory
- Download and launch docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

[Elk successfully configured](https://github.com/Ling354/UofTBootCS/blob/9b4bb90e54c3a582282abae4441b2d0269f69e97/Diagrams/Elk%20container%20screen%20shot%20761.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.1.0.5
- 10.1.0.6

We have installed the following Beats on these machines:
- filebeats
- metricbeats
