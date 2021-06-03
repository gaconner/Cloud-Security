# Cloud-Security
Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available application, in addition to restricting traffic to the network.
What aspect of security do load balancers protect?  load balancer distributes incoming traffic among multiple VMs making it diffulcult for Denial of Service attacks.
What is the advantage of a jump box? A jump box server isntage  a system used to access and manage devices in a separate security zone.The advantage for using
                                     one is that it is a hardened and monitored device that spans two different security zones providing a controlled means of access
                                     between them.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the applications and system servers.
 What does Filebeat watch for? Filebeat collects, parse and visualize ELK logs in a single command.
 What does Metricbeat record? Metrics from the system and services running on the server.

The configuration details of each machine may be found below.\

|-----------------|-----------------------|----------------------------|---------------------------|-------------------|
| Name            | Function              |  IP Address Private        |  IP Address Public        | Operating System  |
|-----------------|-----------------------|----------------------------|---------------------------|-------------------|
|Jump Box         | Gateway               |        10.0.0.4            |     52.188.18.1           |  Linux            |
|-----------------|-----------------------|----------------------------|---------------------------|-------------------|
| Web-1           | Virtual Machine 1     |        10.1.0.12           |         N/A               |  Linux            |
|-----------------|-----------------------|----------------------------|---------------------------|-------------------|
| Web-2           | Virtual Machine 2     |        10.1.0.11           |         N/A               |  Linux            |
|-----------------|-----------------------|----------------------------|---------------------------|-------------------|
| Elk-Server      | Data Analyzer         |        10.2.0.4            |         N/A               |  Linux            |
|-----------------|-----------------------|------------------------   -|------------------   ------|-------------------|

### Access Policies

The machines on the internal network are not exposed to the public Internet. 
Only the Load Balancer machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
40.85.186.22

Machines within the network can only be accessed by Load Balancer and Ansible Container.
Machine allowed to access the ElK VM is at IP address 10.1.0.0/24

A summary of the access policies in place can be found in the table below.
----------------------------------------------------------------------------
|     Name             | Publicly Accessible      |   Allowed IP Addresses |
|----------------------|--------------------------|------------------------|
|    Jump Box          |           No             |      52.188.18.1       |
|----------------------|--------------------------|------------------------|
|    Load Balancer     |          Yes             |      40.85.186.22      |
|----------------------|--------------------------|------------------------|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Ansible provides Configuration Management which promotes lower risk of errors due to manual programming of systems. This also allows multiple systems to be exactly the same.

The playbook implements the following tasks:

1) Add Elasticsearch Repositories.
2) Install Elasticsearch.
3) Install and Set Up Kibana the graphical interface for parsing and interpreting log files.
4) Install and Set Up Logstash which is the tool that collects data from different sources. The data it collects is parsed by Kibana and stored in Elasticsearch.
5) Install Filebeat.

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
WEB1 10.1.0.12
WEB2 10.1.0.11


We have installed the following Beats on these machines:
1) Filebeat
2) Metricbeat

Beats allow for the collection of the following information from each machine:
Filebeat collects data about the file system, ssh traffic / Metricbeat collects machine metrics, such as uptime, cpu usage.

### Using the Playbook

SSH into the control node and follow the steps below:
- Copy the ansible.cfg file to /etc/ansible directory.
- Update the ansible.cfg file to include...
- filebeat-config.yml
- pentest.yml
- metricbeat-config.yml
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

- _Which URL do you navigate to in order to check that the ELK server is running?

