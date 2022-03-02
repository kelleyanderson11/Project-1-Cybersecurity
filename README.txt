## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

"C:\Users\kelle\Documents\Project 1\Diagrams\network diagram.png"

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  "C:\Users\kelle\Documents\Project 1\elk playbook-yml.docx"

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting access to the network.
Load balancer defends an organization against distributed denial of service attacks. A jump box is a secure computer that all admins first connect to before launching any administrative task or use an origination point to connect to other servers. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the date and system logs.
- Filebeat is a lightweight shipper for forwarding and centralizing log date. 
- Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    | DVWA     | 10.0.0.5   | Linux            |
| Web-2    | DVWA     | 10.0.0.6   | Linux            |
| ELK      | ELK      | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 174.86.100.150

Machines within the network can only be accessed by Jump Box container.
- Jump Box Provisioner

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-It allows for the representation of Infrastructure as code and makes it easy to reuse and redeploy. 

The playbook implements the following tasks:
- Installs Docker
  Configures a container
  Downloads an image

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-Web-1 and Web-2
 
We have installed the following Beats on these machines:
-Filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
-Filebeat monitors the log files and forward them to Elasticsearch and Logstash for indexing. Metricbeat collects metrics from the operating system. 



### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat playbook.yml file to /etc/ansible/.
- Update the config file to include...
- Run the playbook, and navigate to kabana to check that the installation worked as expected.



