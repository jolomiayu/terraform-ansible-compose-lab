Terraform + Ansible + Docker Compose Lab 🚀

Project Overview

This project demonstrates Infrastructure as Code (IaC), Configuration Management, and Container Deployment on AWS.

Using Terraform, an EC2 instance and security group are provisioned automatically. Ansible is then used to configure the server, install Docker and Docker Compose, and deploy a multi-container application.

The project showcases a complete DevOps workflow from infrastructure provisioning to automated application deployment.

---

Architecture

Terraform
    ↓
EC2 Instance + Security Group
    ↓
Ansible
    ↓
Docker Installation
    ↓
Docker Compose Installation
    ↓
Multi-Container Deployment

frontend (nginx)
        ↓
backend (http-echo)

---

Technologies Used

- AWS EC2
- Terraform
- Ansible
- Docker
- Docker Compose
- Linux
- SSH

---

Features

- Infrastructure provisioning with Terraform
- Security group automation
- Ansible inventory management
- Docker installation automation
- Docker Compose installation automation
- Automated deployment using Ansible
- Multi-container application deployment
- Container lifecycle troubleshooting

---

Project Structure

terraform/
├── provider.tf
├── main.tf
├── outputs.tf

ansible/
├── inventory
├── docker-compose.yml
├── app-compose.yml
├── deploy-compose.yml

---

Deployment Workflow

1. Provision Infrastructure

terraform init
terraform apply

2. Verify Connectivity

ansible web -i inventory -m ping

3. Install Docker and Docker Compose

ansible-playbook -i inventory docker-compose.yml

4. Deploy Application

ansible-playbook -i inventory deploy-compose.yml

---

Screenshots

Terraform Output

"Terraform Output" (screenshots/terraform-output.png)

Ansible Connectivity Test

"Ansible Ping" (screenshots/ansible-ping.png)

Docker Compose Installation

"Docker Compose Version" (screenshots/docker-compose-version.png)

Automated Deployment

"Ansible Deployment" (screenshots/ansible-deployment.png)

Running Containers

"Docker PS" (screenshots/docker-ps.png)

---

Lessons Learned

During deployment, the frontend service was renamed from "web" to "frontend".

This caused Docker Compose to detect an orphan container and report a port allocation conflict.

The issue was resolved using:

docker compose down --remove-orphans

This provided practical experience with Docker Compose troubleshooting and container lifecycle management.

---

Key Learning Outcomes

- Infrastructure as Code with Terraform
- Configuration Management with Ansible
- Docker installation and management
- Docker Compose deployment
- Multi-container application architecture
- Automated deployment workflows
- Troubleshooting container deployment issues
- AWS infrastructure management

---

Author

Jolomi Ayu

Cloud / DevOps Engineering Portfolio Project
