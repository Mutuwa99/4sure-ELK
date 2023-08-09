# ELK Stack with Docker Monitoring and Log Forwarding By Noble Mulaudzi

This repository contains Ansible code to set up a robust ELK (Elasticsearch, Logstash, Kibana) stack, coupled with Docker monitoring using cAdvisor and log forwarding using Filebeat.

![Alt Text](./elk_final.png)

## Architecture Overview

The architecture consists of the following components:

1. **Docker Containers:** Running applications and generating logs.
2. **cAdvisor:** Monitoring Docker containers and collecting performance metrics.
3. **Filebeat:** Collecting logs from Docker containers and cAdvisor.
4. **Logstash:** Processing and transforming logs from Filebeat.
5. **Elasticsearch:** Storing and indexing the processed log data.
6. **Kibana:** Providing a visual interface for log data exploration and analysis.

## Instructions

1. Ensure you have Ansible installed on your local machine.
2. Clone this repository to your local system.

### ELK Stack Installation

1. Update the `inventory/production` file with your server's IP address, SSH username, and private key file path.
2. Modify the `ansible/roles/elk/tasks/main.yml` file as needed for Elasticsearch, Logstash, and Kibana installation.

### Docker Monitoring and Log Forwarding

1. Update the `ansible/roles/monitoring_agents/files/filebeat.yml` configuration file to include the appropriate Elasticsearch host.
2. Place your Docker-specific configuration files, if needed, in the `ansible/roles/monitoring_agents/files/` directory.

### Run the Playbook

Execute the following command in your terminal to deploy the ELK stack and monitoring agents:

```bash
ansible-playbook -i inventory/production playbooks/main.yml



### Tutorial by Noble Mutuwa Isaya