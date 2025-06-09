# 🚀 EC2-Deployment Project

![Project Logo](assets/img/logo.png)

## Automated Web Application Deployment to AWS EC2

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/matthewntsiful/ec2-deployment/ec2.yml?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/matthewntsiful/ec2-deployment?style=flat-square)

## Built With

![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=apache&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![SSH](https://img.shields.io/badge/SSH-4D4D4D?style=for-the-badge&logo=windows-terminal&logoColor=white)

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Deployment Workflow](#-deployment-workflow)
- [Prerequisites](#-prerequisites)
- [Setup Instructions](#-setup-instructions)
- [GitHub Secrets Configuration](#-github-secrets-configuration)
- [Customization](#-customization)
- [Contributing](#-contributing)
- [License](#-license)

## 🔍 Overview

This project demonstrates an automated deployment pipeline that deploys a simple web application to AWS EC2 instances using GitHub Actions. The workflow supports three separate environments (Development, Testing, and Production), each with its own configuration and secrets. When code is pushed to the main branch, the workflow automatically deploys the updated application to the appropriate environment, while ignoring README.md changes to prevent unnecessary deployments.

## ✨ Features

- **Multi-Environment Deployment**: Separate deployment pipelines for Development, Testing, and Production environments
- **Continuous Deployment**: Automatic deployment to EC2 on push to main branch
- **Selective Deployment Triggers**: Path-ignore configuration to prevent unnecessary deployments (e.g., README updates)
- **Secure Credential Management**: Using GitHub Secrets for secure credential storage
- **Apache Web Server**: Automatic installation and configuration of Apache
- **Minimal Web Application**: Simple responsive web design with custom styling

## 📁 Project Structure

```markdown
ec2-deploy/
├── .github/
│   └── workflows/
│       └── ec2.yml        # GitHub Actions workflow file with multi-environment support
├── assets/
│   └── img/
│       ├── background.jpg # Background image for the web app
│       └── logo.png       # Logo image
├── index.html             # Main HTML file
├── style.css              # CSS styling
└── README.md              # Project documentation (excluded from deployment triggers)
```

## 🔄 Deployment Workflow

1. Code is pushed to the main branch (README.md changes are ignored via path-ignore)
2. GitHub Actions workflow is triggered for the appropriate environment (Development, Testing, or Production)
3. Code is checked out
4. Files are deployed to the corresponding EC2 instance via SSH
5. Remote commands install/configure Apache
6. Web application is moved to the appropriate directory
7. Application is accessible via the environment-specific EC2 public DNS/IP

## 📋 Prerequisites

- AWS account with multiple EC2 instances (for Development, Testing, and Production)
- SSH key pairs for each EC2 instance
- GitHub repository with environments configured
- Basic knowledge of GitHub Actions and environment secrets
- Understanding of web development fundamentals

## 🛠 Setup Instructions

### 1. EC2 Instance Setup

1. Launch an EC2 instance with Ubuntu
2. Configure security group to allow HTTP (port 80) and SSH (port 22)
3. Connect to your instance and ensure it's updated:

```bash
sudo apt-get update
sudo apt-get upgrade
```

### 2. Repository Setup

1. Fork or clone this repository
2. Update the web application files as needed
3. Configure GitHub Secrets (see below)
4. Push changes to the main branch to trigger deployment

## 🔐 GitHub Secrets Configuration

Configure the following secrets in your GitHub repository environments (Development, Testing, Production):

| Secret Name | Description |
|-------------|-------------|
| `EC2_SSH_KEY` | Private SSH key for EC2 instance (content of .pem file) |
| `HOST_DNS` | Public DNS or IP of your EC2 instance |
| `EC2_USER` | Username for SSH connection (e.g., ubuntu, ec2-user) |
| `TARGET_DIR` | Target directory on EC2 (e.g., /home/ubuntu) |

Each environment (Development, Testing, Production) has its own set of these secrets, allowing for deployment to different servers.

## 🎨 Customization

### Web Application

- Replace `background.jpg` and `logo.png` with your own images
- Modify `index.html` to include your content
- Update `style.css` to match your branding

### Workflow

- The workflow is configured with path-ignore to prevent README.md updates from triggering deployments
- Three separate environments are configured: Development, Testing, and Production
- Each environment uses its own set of secrets for deployment
- Edit `.github/workflows/ec2.yml` to add additional deployment steps
- Customize the Apache configuration as needed
- Modify environment-specific configurations as required

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔮 Future Enhancements

The EC2-Deploy project roadmap includes several exciting enhancements:

### Short-term Goals

- **Security Scanning Integration**: Implement SonarQube and Snyk scans for code quality and vulnerability detection
- ✅ **Multi-environment Support**: Extend deployment to development, testing, and production environments (Completed)
- **Monitoring Integration**: Add CloudWatch metrics and alerts for application health monitoring
- **HTTPS Implementation**: Configure SSL/TLS certificates for secure connections

### Mid-term Goals

- **Container Integration**: Migrate to Docker containers for consistent deployment
- **CI/CD Pipeline Expansion**: Add automated testing and quality gates
- **Security Automation**: Implement automated security checks with Snyk for dependency scanning and SonarQube for code quality analysis
- **Blue/Green Deployment**: Implement zero-downtime deployment strategy

### Long-term Vision

- **Infrastructure as Code**: Complete AWS infrastructure management using Terraform or CloudFormation
- **Microservices Architecture**: Break down the application into scalable microservices
- **Auto-scaling Configuration**: Implement dynamic scaling based on traffic patterns
- **Security-as-Code**: Fully integrate security scanning into the development lifecycle with SonarQube for static code analysis and Snyk for continuous vulnerability monitoring
- **Compliance Automation**: Implement automated compliance checks and reporting for regulatory requirements

---

## Technologies Used

![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=apache&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![SSH](https://img.shields.io/badge/SSH-4D4D4D?style=for-the-badge&logo=windows-terminal&logoColor=white)

Powered by BlakkBrother Inc.

© 2023 BlakkBrother Inc.
All rights reserved.
