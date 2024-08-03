# Deployment of FastAPI app with Ansible

This repository contains Ansible playbooks and configurations to deploy a FastAPI application. The deployment process includes setting up the necessary infrastructure, installing dependencies, and configuring the FastAPI application.


## Task Requirements
Overview: You will be assigned one of the 7 boilerplates from Stage 4. Your task is to set up a new instance of the assigned boilerplate using Infrastructure as Code (IaC) with Ansible. The setup should include the following:
- Clone the DevOps branch of your boilerplate repository to a Linux server.
- Deploy the boilerplate application on the server.
- Install Dependencies:
- Setup PostgreSQL:
- Configure a PostgreSQL database.
- Save the admin user and credentials in /var/secrets/pg_pw.txt.
- Ensure your application starts on port 3000.
- Set up Nginx to reverse proxy your application to port 80.
- Configure stderr logs to be saved in /var/log/stage_5b/error.log and stdout logs in /var/log/stage_5b/out.log.


## Prerequisites
Before you begin, ensure you have the following installed:
- Ansible: Version 2.9 or higher
- Python: Version 3.6 or higher
- A target server: This could be a local VM, cloud instance, or physical server running a Unix-like OS (e.g., Ubuntu).


## Ansible Scripts
For this project I made use of ansible roles to modularise my script and make it easy to debug in the case of an error. My scripts includes `hosts.ini`, `playbook.yml`, `ansible.cfg`, and different role directory for each aspect of the application deployment. To pass environmental variables and the new configuration for nginx, I used jinja template file to declare the variables and send to the nginx.conf.d directory

## Usage
The command to run the ansible script is `ansible-playbook -i hosts.ini playbook.yml`
