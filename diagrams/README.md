## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![/diagrams/Rednetwork.png](https://github.com/Isalaz0297/CyberSecurity-Projects/blob/main/diagrams/Elk-network.png)https://github.com/Isalaz0297/CyberSecurity-Projects/blob/main/diagrams/Rednetwork.png
![/diagrams/Elk-network.png](https://github.com/Isalaz0297/CyberSecurity-Projects/blob/main/diagrams/Elk-network.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the *elk.yml* file may be used to install only certain pieces of it, such as Filebeat.

  - _elk.yml_

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be *highly available*, in addition to restricting a DoS attack to the network.
-  Load balancers allow for the availability of a machine creating redundancy. If one machine goes down or is overwhelmed the load balancer can allow traffic to the other backup machines. A jumpbox is used to create a process data to the web server. The machine is secure and is an origin to connect to other untrusted servers.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system data.
- _Log files and log events_
- _Metrics and statistics from the operating system and services_

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    |web-server| 10.0.0.5   | Linux            |
| Web 2    |web-server| 10.0.0.6   | Linux            |
| Web 3    |web-server| 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ELK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _10.0.0.4_

Machines within the network can only be accessed by SSH.
- _The ELK VM can only be accessed by the Anisble docker container in the jumpbox *10.0.0.4*_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | Personal machine IP  |
| Web(s)   | Yes                 | Any                  |
| ELK      | No                  | 10.0.0.4
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _Runs on linux as well as windows, and is easy to set up and use_

The playbook implements the following tasks:
- _First the playbook will install docker
- _Install python
- _Download and launch a docker elk container. Then enable ELK's services

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![CyberSecurity-Projects/Images/docker_ps.png](https://github.com/Isalaz0297/CyberSecurity-Projects/blob/main/images/Docker_ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _10.0.0.5, 10.0.0.6, 10.0.0.7_

We have installed the following Beats on these machines:
- _Filebeat, and Metricbeat_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the elk.yml file to ansible.cfg.
- Update the elk.yml file to include more memory
- Run the playbook, and navigate to the docker elk container to check that the installation worked as expected.

- _elk.yml_ copy it too the the anisble configuration file.
- _Anisble hosts file by allowing ansible to access VMs through their specific IP addresses._
- _http://10.1.0.4:5601/app/kibana_

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
