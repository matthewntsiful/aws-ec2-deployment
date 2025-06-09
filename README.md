# 🚀 EC2-Deployment Project

<div align="center">
  <img src="assets/img/logo.png" alt="Project Logo" width="200"/>
  <br>
  <h3>Automated Web Application Deployment to AWS EC2</h3>
  
  ![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/username/ec2-deploy/ec2.yml?style=flat-square)
  ![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
  ![GitHub last commit](https://img.shields.io/github/last-commit/username/ec2-deploy?style=flat-square)
  
  <h4>Built With</h4>
  <p>
    <img src="https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS EC2"/>
    <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions"/>
    <img src="https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=apache&logoColor=white" alt="Apache"/>
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
    <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
    <img src="https://img.shields.io/badge/SSH-4D4D4D?style=for-the-badge&logo=windows-terminal&logoColor=white" alt="SSH"/>
  </p>
</div>

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

This project demonstrates an automated deployment pipeline that deploys a simple web application to an AWS EC2 instance using GitHub Actions. When code is pushed to the main branch, the workflow automatically deploys the updated application to the configured EC2 server.

## ✨ Features

- **Continuous Deployment**: Automatic deployment to EC2 on push to main branch
- **Secure Credential Management**: Using GitHub Secrets for secure credential storage
- **Apache Web Server**: Automatic installation and configuration of Apache
- **Minimal Web Application**: Simple responsive web design with custom styling

## 📁 Project Structure

```
ec2-deploy/
├── .github/
│   └── workflows/
│       └── ec2.yml        # GitHub Actions workflow file
├── assets/
│   └── img/
│       ├── background.jpg # Background image for the web app
│       └── logo.png       # Logo image
├── index.html             # Main HTML file
├── style.css              # CSS styling
└── README.md              # Project documentation
```

## 🔄 Deployment Workflow

1. Code is pushed to the main branch
2. GitHub Actions workflow is triggered
3. Code is checked out
4. Files are deployed to EC2 via SSH
5. Remote commands install/configure Apache
6. Web application is moved to the appropriate directory
7. Application is accessible via the EC2 public DNS/IP

## 📋 Prerequisites

- AWS account with an EC2 instance
- SSH key pair for EC2 instance
- GitHub repository
- Basic knowledge of GitHub Actions
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

Configure the following secrets in your GitHub repository:

| Secret Name | Description |
|-------------|-------------|
| `EC2_SSH_KEY` | Private SSH key for EC2 instance (content of .pem file) |
| `HOST_DNS` | Public DNS or IP of your EC2 instance |
| `EC2_USER` | Username for SSH connection (e.g., ubuntu, ec2-user) |
| `TARGET_DIR` | Target directory on EC2 (e.g., /home/ubuntu) |

## 🎨 Customization

### Web Application

- Replace `background.jpg` and `logo.png` with your own images
- Modify `index.html` to include your content
- Update `style.css` to match your branding

### Workflow

- Edit `.github/workflows/ec2.yml` to add additional deployment steps
- Customize the Apache configuration as needed
- Add environment-specific configurations

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
- **Multi-environment Support**: Extend deployment to development, staging, and production environments
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

<div align="center">
  <h4>Technologies Used</h4>
  <p>
    <img src="https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS EC2"/>
    <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions"/>
    <img src="https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=apache&logoColor=white" alt="Apache"/>
    <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu"/>
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
    <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
    <img src="https://img.shields.io/badge/SSH-4D4D4D?style=for-the-badge&logo=windows-terminal&logoColor=white" alt="SSH"/>
  </p>
  <p>Powered by BlakkBrother Inc.</p>
  <p>© 2023 BlakkBrother Inc.</p>
</div>