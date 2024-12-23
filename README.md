
# Automated Network Deployment Project

This repository contains scripts and configurations to automate the deployment of a web-based application using Terraform, Ansible, Docker, and Azure DevOps pipelines. The project provisions infrastructure, sets up configurations, and deploys an HTML application hosted on an Nginx container.

---

## Features

- **Infrastructure Provisioning**: Uses Terraform to set up Azure Virtual Machines (VMs) and networking.
- **Configuration Management**: Ansible is used to configure the VM and install necessary software.
- **CI/CD Pipeline**: GitHub Actions automate the deployment process.
- **Containerization**: The application is containerized using Docker for easy deployment.

---

## Project Structure

### Configurations

- **`.gitignore`**: Specifies files and directories to exclude from version control.
- **`ansible.cfg`**: Configures Ansible's behavior, such as inventory and SSH settings.
- **`inventory.ini`**: Defines the target hosts and SSH details for Ansible.
- **`network-vm.pem`**: Private SSH key for VM access (not shared publicly).

### Terraform Files

- **`main.tf`**: Provisions the Azure infrastructure.
- **`variables.tf`**: Defines input variables for Terraform.
- **`outputs.tf`**: Outputs important information, such as the public IP of the VM.

### Scripts

- **`playbook.yml`**: Ansible playbook for configuring the VM and deploying the application.
- **`azure-pipelines.yml`**: CI/CD pipeline configuration using GitHub Actions.
- **`deploy.yml`**: Workflow for deploying the application via Terraform and Ansible.

### Web Application

- **`Dockerfile`**: Builds a lightweight Nginx container to serve the HTML application.
- **`index.html`**: A simple HTML page that is hosted on the Nginx server.

---

## Getting Started

### Prerequisites

- **Tools**:
  - [Terraform](https://www.terraform.io/)
  - [Ansible](https://www.ansible.com/)
  - [Docker](https://www.docker.com/)
  - [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/)
  - [Python 3.9+](https://www.python.org/)
- **Environment**:
  - Azure account with proper permissions.
  - GitHub repository secrets for Azure credentials.

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ramsair/networks-ca-1.git
   cd networks-ca-1
 

2. Trigger the CI/CD pipeline:
   - Push changes to the `main` branch to activate GitHub Actions.

---

## Usage

- Access the deployed application using the public IP provided by Terraform outputs:
  ```bash
  http://13.64.214.173/
  ```
- The HTML application will display the following:
  ```html
  <h1>Welcome to the Sample HTML Application!</h1>
  ```

---

## Troubleshooting

- **Terraform Errors**:
  - Check the variables in `variables.tf` for correct values.
  - Ensure Azure credentials are set up correctly.
- **Ansible Issues**:
  - Verify SSH connectivity using the provided private key.
  - Check `inventory.ini` for the correct public IP.
- **Pipeline Failures**:
  - Ensure secrets (Azure credentials) are configured in GitHub.


