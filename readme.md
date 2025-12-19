# Production-Ready Three-Tier Web Application on AWS EKS

## 🎯 Project Overview
This project demonstrates a complete DevOps implementation: deploying a modern three-tier application (React, Node.js, MongoDB) on AWS EKS with a fully automated CI/CD pipeline and GitOps workflow. The infrastructure is entirely defined as code using Terraform, showcasing best practices for scalability, security, and maintainability in a cloud-native environment.

## 📊 Architecture Diagram
(assets/Three-Tier.gif)

Architecture Flow:
1.  CI/CD Pipeline (Jenkins): Developers push code to GitHub, triggering an automated pipeline that builds Docker images, runs security scans, and pushes them to Amazon ECR.
2.  GitOps Deployment (ArgoCD): ArgoCD automatically syncs the Kubernetes manifests from the Git repository, deploying the new application versions to the AWS EKS cluster.
3.  Application Layer: The React frontend serves the UI, the Node.js backend handles business logic, and MongoDB manages data persistence—all running as containers within Kubernetes.
4.  Observability: Prometheus collects metrics, and Grafana provides operational dashboards for real-time monitoring of the cluster and application health.

## 🛠️ Technologies Used
Category 	                        Tools 
Cloud Provider	                  AWS 
Infrastructure as Code	          Terraform 
Container Orchestration	          Kubernetes (EKS), Helm
CI/CD & GitOps	                  Jenkins, ArgoCD, SonarQube
Containers	                      Docker 
Monitoring & Observability	      Prometheus, Grafana
Application Stack	                React.js, Node.js, MongoDB, Nginx

## 🚀 My Implementation & Role
As the sole DevOps engineer for this project, I was responsible for the end-to-end design, implementation, and documentation. This involved:

### 1. Infrastructure Provisioning with Terraform
- Wrote reusable Terraform modules to provision the core AWS network (VPC, subnets, gateways).
- Automated the creation of the EKS cluster with managed node groups for cost-effectiveness and easier scaling.
- Implemented secure configurations for IAM roles, security groups, and ECR repositories.

### 2. Building the CI/CD Pipeline with Jenkins
- Designed and implemented a Jenkins declarative pipeline integrating multiple stages:
  - Code Checkout & Build: Compiles the application code.
  - Static Code Analysis: Integrated SonarQube for code quality gates.
  - Docker Image Build & Security Scan: Built optimized images and scanned for vulnerabilities.
  - Push to ECR: Securely stored images in a private Amazon Elastic Container Registry.
- Configured webhooks for automatic pipeline triggers on Git commits.

### 3. Kubernetes Deployment & GitOps
- Developed comprehensive Kubernetes manifests (Deployments, Services, ConfigMaps, Secrets) for all application components.
- Configured Ingress with the AWS Load Balancer Controller to expose the application securely.
- Set up ArgoCD for a GitOps workflow, ensuring the EKS cluster state always matched the declared state in the Git repository, enabling easy rollbacks and audit trails.

### 4. Monitoring & Logging Setup
- Deployed the Prometheus & Grafana stack using Helm charts for monitoring.
- Customized Grafana dashboards to visualize cluster resource usage (CPU, Memory), application performance, and pod health.
- Configured alerting rules to proactively identify issues.

## 📁 Repository Structure
TWSThreeTierAppChallenge/ # Your Forked Repo Name
├── Application-Code/ # React Frontend & Node.js Backend source
├── Jenkins-Pipeline-Code/ # Jenkinsfile & Pipeline scripts
├── Jenkins-Server-TF/ # Terraform code for Jenkins server
├── Kubernetes-Manifests-Files/# K8s YAML files for app & tools
├── assets/ # Architecture diagrams & screenshots
└── README.md # This file

## 🚀 Deployment Overview
This infrastructure is fully defined as code and can be reproduced by following the core DevOps workflow it demonstrates:
1. Provision Infrastructure: The AWS EKS cluster, VPC, and supporting services are provisioned using Terraform.
2. Bootstrap CI/CD: A Jenkins server runs the pipeline that builds, scans, and pushes Docker images to Amazon ECR.
3. Deploy with GitOps: ArgoCD synchronizes the Kubernetes manifests to deploy the application.


### 🧠 Key Learnings & Outcomes
- End-to-End Automation: Successfully connected the entire software delivery chain—from code commit to production deployment—with minimal manual intervention.
- Infrastructure as Code Mastery: Gained deep practical experience managing complex cloud infrastructure using Terraform, ensuring repeatability and version control.
- GitOps in Practice: Implemented ArgoCD to manage Kubernetes deployments, which significantly improved deployment reliability and rollback capabilities.
- Problem-Solving: Addressed real-world challenges such as configuring IAM permissions for EKS, managing persistent storage for MongoDB, and optimizing Docker image sizes.
