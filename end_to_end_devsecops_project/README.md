# End-to-End DevSecOps CI/CD Pipeline on AWS EKS

An end-to-end DevSecOps project that automates application testing, code-quality analysis, containerization, vulnerability scanning, infrastructure provisioning, Kubernetes deployment, monitoring, and alerting.

This project integrates **GitLab CI/CD, Docker, DockerHub, SonarQube, Trivy, Terraform, Kubernetes, Amazon EKS, Prometheus, Grafana, and Alertmanager** into a complete DevSecOps workflow.

---

## Project Architecture

The following diagrams provide an overview of the project architecture and repository structure.

### Project Architecture

<a href="docs/architecture/Project_Architecture.png">
  <img src="docs/architecture/Project_Architecture.png" width="1200" alt="Project Architecture">
</a>

### DevSecOps Architecture Overview

<a href="docs/architecture/Project_Architecture_overview.jpg">
  <img src="docs/architecture/Project_Architecture_overview.jpg" width="1200" alt="End-to-End DevSecOps Project Architecture Overview">
</a>

### Repository Structure

<a href="docs/architecture/Project_repo.png">
  <img src="docs/architecture/Project_repo.png" width="1200" alt="Project Repository Structure">
</a>

---

## CI/CD Pipeline

GitLab CI/CD automates the application lifecycle from testing through security validation and deployment.

### Pipeline Flow

```text
GitLab
   |
   v
Application Tests
   |
   v
SonarQube Analysis
   |
   v
Docker Build
   |
   v
DockerHub
   |
   v
Trivy Security Scan
   |
   v
Kubernetes / Amazon EKS
   |
   v
Application Validation
```

### Pipeline Stages

<a href="docs/screenshots/ci-cd/all_stages_Passed.png">
  <img src="docs/screenshots/ci-cd/all_stages_Passed.png" width="1200" alt="All CI/CD Pipeline Stages Passed">
</a>

---

## Docker

Docker is used to containerize the application before publishing the image to DockerHub.

### Dockerfile Configuration

<a href="docs/screenshots/docker/dockerfile_configuration1.png">
  <img src="docs/screenshots/docker/dockerfile_configuration1.png" width="1200" alt="Dockerfile Configuration">
</a>

### Docker Image

<a href="docs/screenshots/docker/docker_image1.png">
  <img src="docs/screenshots/docker/docker_image1.png" width="1200" alt="Docker Image">
</a>

### DockerHub Image

<a href="docs/screenshots/docker/dockerhub_image1.png">
  <img src="docs/screenshots/docker/dockerhub_image1.png" width="1200" alt="DockerHub Container Image">
</a>

### Docker Test

<a href="docs/screenshots/docker/test_pass1.png">
  <img src="docs/screenshots/docker/test_pass1.png" width="1200" alt="Docker Test Passed">
</a>

### Automated Test Addition

<a href="docs/screenshots/docker/added_test1.png">
  <img src="docs/screenshots/docker/added_test1.png" width="1200" alt="Automated Test Added">
</a>

---

## Infrastructure as Code

Terraform is used to provision the AWS infrastructure required for the Kubernetes environment.

### Terraform Apply

<a href="docs/screenshots/kubernetes/01_terraform_apply_complete.png">
  <img src="docs/screenshots/kubernetes/01_terraform_apply_complete.png" width="1200" alt="Terraform Apply Completed Successfully">
</a>

---

## Kubernetes and Amazon EKS

The application is deployed to Kubernetes running on Amazon EKS.

### Kubernetes Nodes

<a href="docs/screenshots/kubernetes/02_kubernetes_nodes_ready.png">
  <img src="docs/screenshots/kubernetes/02_kubernetes_nodes_ready.png" width="1200" alt="Kubernetes Nodes Ready">
</a>

### Kubernetes Cluster Information

<a href="docs/screenshots/kubernetes/03_kubernetes_cluster_info.png">
  <img src="docs/screenshots/kubernetes/03_kubernetes_cluster_info.png" width="1200" alt="Kubernetes Cluster Information">
</a>

### Kubernetes System Pods

<a href="docs/screenshots/kubernetes/04_kubernetes_system_pods.png">
  <img src="docs/screenshots/kubernetes/04_kubernetes_system_pods.png" width="1200" alt="Kubernetes System Pods">
</a>

### AWS EKS Cluster

<a href="docs/screenshots/aws/eks_cluster1.png">
  <img src="docs/screenshots/aws/eks_cluster1.png" width="1200" alt="Amazon EKS Cluster">
</a>

### EKS Application Pods

<a href="docs/screenshots/aws/EKS Application Pods Running Successfully1.png">
  <img src="docs/screenshots/aws/EKS Application Pods Running Successfully1.png" width="1200" alt="EKS Application Pods Running Successfully">
</a>

---

## Kubernetes Load Balancing and Ingress

The project uses the AWS Load Balancer Controller and Kubernetes Ingress to expose the application.

### Load Balancer Controller IAM Policy

<a href="docs/screenshots/kubernetes/07_load_balancer_controller_iam_policy.png">
  <img src="docs/screenshots/kubernetes/07_load_balancer_controller_iam_policy.png" width="1200" alt="AWS Load Balancer Controller IAM Policy">
</a>

### Load Balancer Controller Service Account

<a href="docs/screenshots/kubernetes/08_lb_controller_iam_serviceaccount.png">
  <img src="docs/screenshots/kubernetes/08_lb_controller_iam_serviceaccount.png" width="1200" alt="Load Balancer Controller IAM Service Account">
</a>

### Kubernetes Load Balancer Service Account

<a href="docs/screenshots/kubernetes/09_lb_controller_serviceaccount.png">
  <img src="docs/screenshots/kubernetes/09_lb_controller_serviceaccount.png" width="1200" alt="Load Balancer Controller Service Account">
</a>

### Kubernetes Service

<a href="docs/screenshots/aws/Kubernetes Service Successfully Created1.png">
  <img src="docs/screenshots/aws/Kubernetes Service Successfully Created1.png" width="1200" alt="Kubernetes Service Successfully Created">
</a>

### AWS Load Balancer

<a href="docs/screenshots/aws/load_balancer1.png">
  <img src="docs/screenshots/aws/load_balancer1.png" width="1200" alt="AWS Load Balancer">
</a>

### AWS Application Load Balancer Provisioned Through Kubernetes Ingress

<a href="docs/screenshots/aws/AWS Application Load Balancer Successfully Provisioned Through Kubernetes Ingress1.png">
  <img src="docs/screenshots/aws/AWS Application Load Balancer Successfully Provisioned Through Kubernetes Ingress1.png" width="1200" alt="AWS Application Load Balancer Successfully Provisioned Through Kubernetes Ingress">
</a>

### Application Running

<a href="docs/screenshots/aws/actual application1.png">
  <img src="docs/screenshots/aws/actual application1.png" width="1200" alt="Deployed Application Running">
</a>

### EC2 Instances

<a href="docs/screenshots/aws/ec2_instances1.png">
  <img src="docs/screenshots/aws/ec2_instances1.png" width="1200" alt="AWS EC2 Instances">
</a>

---

## DevSecOps Security

Security is integrated into the CI/CD workflow through SonarQube and Trivy.

---

## SonarQube

SonarQube provides static code analysis and code-quality/security analysis.

### GitLab Pipeline Success

<a href="docs/screenshots/security/SonarQube/gitlab_pipeline_sucess1.png">
  <img src="docs/screenshots/security/SonarQube/gitlab_pipeline_sucess1.png" width="1200" alt="GitLab Pipeline Successful">
</a>

### SonarQube Analysis History

<a href="docs/screenshots/security/SonarQube/sonarqube_analysis_history.png -1 .png">
  <img src="docs/screenshots/security/SonarQube/sonarqube_analysis_history.png -1 .png" width="1200" alt="SonarQube Analysis History">
</a>

### SonarQube Project Overview

<a href="docs/screenshots/security/SonarQube/sonarqube_project_overview1 .png">
  <img src="docs/screenshots/security/SonarQube/sonarqube_project_overview1 .png" width="1200" alt="SonarQube Project Overview">
</a>

### SonarQube Quality Gate

<a href="docs/screenshots/security/SonarQube/sonarqube_quality_gate1.png">
  <img src="docs/screenshots/security/SonarQube/sonarqube_quality_gate1.png" width="1200" alt="SonarQube Quality Gate">
</a>

### SonarQube Security Issues

<a href="docs/screenshots/security/SonarQube/sonarqube_security_issues.png -1.png">
  <img src="docs/screenshots/security/SonarQube/sonarqube_security_issues.png -1.png" width="1200" alt="SonarQube Security Issues">
</a>

---

## Trivy

Trivy scans container images for known vulnerabilities before deployment.

### Trivy Image Scan

<a href="docs/screenshots/security/Trivy_image_scan/Screenshot1.png">
  <img src="docs/screenshots/security/Trivy_image_scan/Screenshot1.png" width="1200" alt="Trivy Image Scan">
</a>

### Trivy Scan Added to Pipeline

<a href="docs/screenshots/security/Trivy_image_scan/trivy_image_scan_added1.png">
  <img src="docs/screenshots/security/Trivy_image_scan/trivy_image_scan_added1.png" width="1200" alt="Trivy Image Scan Added to CI/CD Pipeline">
</a>

---

## Monitoring and Observability

The project uses **Prometheus, Grafana, and Alertmanager** for monitoring, metrics collection, dashboards, and alerting.

### Prometheus Stack Installation

<a href="docs/screenshots/monitoring/10_prometheus_stack_installed1.png">
  <img src="docs/screenshots/monitoring/10_prometheus_stack_installed1.png" width="1200" alt="Prometheus Stack Installed">
</a>

### Observability Pods

<a href="docs/screenshots/monitoring/11_observability_pods_running1.png">
  <img src="docs/screenshots/monitoring/11_observability_pods_running1.png" width="1200" alt="Observability Pods Running">
</a>

### Prometheus and Grafana Connection

<a href="docs/screenshots/ci-cd/Prometheus_Grafana_connection1.png">
  <img src="docs/screenshots/ci-cd/Prometheus_Grafana_connection1.png" width="1200" alt="Prometheus and Grafana Connection">
</a>

### Prometheus Query

<a href="docs/screenshots/ci-cd/Prometheus_query1.png">
  <img src="docs/screenshots/ci-cd/Prometheus_query1.png" width="1200" alt="Prometheus Query">
</a>

### Prometheus Service Monitoring

<a href="docs/screenshots/ci-cd/Prometheus_svc_monitoring1.png">
  <img src="docs/screenshots/ci-cd/Prometheus_svc_monitoring1.png" width="1200" alt="Prometheus Service Monitoring">
</a>

### Grafana Dashboard

<a href="docs/screenshots/ci-cd/Grafana_dashboard1.png">
  <img src="docs/screenshots/ci-cd/Grafana_dashboard1.png" width="1200" alt="Grafana Dashboard">
</a>

---

## Alerting

Alertmanager is configured to detect firing alerts and support notification delivery.

### Alertmanager

<a href="docs/screenshots/ci-cd/alertmanager.png">
  <img src="docs/screenshots/ci-cd/alertmanager.png" width="1200" alt="Alertmanager">
</a>

### Alertmanager Alert

<a href="docs/screenshots/ci-cd/Alertmanager_alert.png">
  <img src="docs/screenshots/ci-cd/Alertmanager_alert.png" width="1200" alt="Alertmanager Alert">
</a>

### Prometheus Alert

<a href="docs/screenshots/ci-cd/Prometheus_alert1.png">
  <img src="docs/screenshots/ci-cd/Prometheus_alert1.png" width="1200" alt="Prometheus Alert">
</a>

### Grafana Firing Alert

<a href="docs/screenshots/ci-cd/Grafana_firing_alert1.png">
  <img src="docs/screenshots/ci-cd/Grafana_firing_alert1.png" width="1200" alt="Grafana Firing Alert">
</a>

### Gmail Alert

<a href="docs/screenshots/ci-cd/Gmail_alert.png">
  <img src="docs/screenshots/ci-cd/Gmail_alert.png" width="1200" alt="Gmail Alert Notification">
</a>

---

## Technologies

| Area           | Technologies                      |
| -------------- | --------------------------------- |
| Cloud          | AWS, Amazon EKS                   |
| Infrastructure | Terraform                         |
| CI/CD          | GitLab CI/CD                      |
| Containers     | Docker, DockerHub                 |
| Security       | SonarQube, Trivy                  |
| Orchestration  | Kubernetes                        |
| Monitoring     | Prometheus, Grafana, Alertmanager |
| Application    | Node.js                           |

---

## DevSecOps Concepts Demonstrated

- Infrastructure as Code with Terraform
- Continuous Integration and Continuous Delivery
- Automated application testing
- Containerization with Docker
- Container image management with DockerHub
- Kubernetes orchestration
- Amazon EKS deployment
- AWS Load Balancer Controller
- Kubernetes Ingress
- Static code analysis with SonarQube
- Container vulnerability scanning with Trivy
- Prometheus metrics collection
- Grafana monitoring dashboards
- Alertmanager alerting
- Email notifications
- Security integrated into CI/CD

---

## Project Evidence

The screenshots throughout this README provide evidence of the actual implementation across AWS, GitLab, Docker, Kubernetes, SonarQube, Trivy, Prometheus, Grafana, and Alertmanager.

**Click any screenshot to open the original full-resolution image.**

---

## Resume Version

### End-to-End DevSecOps CI/CD Pipeline — AWS EKS

- Built an end-to-end GitLab CI/CD pipeline automating application testing, SonarQube analysis, Docker image build and publishing, Trivy vulnerability scanning, and deployment to Amazon EKS.
- Provisioned AWS infrastructure using Terraform and deployed a containerized application to Kubernetes.
- Configured AWS Load Balancer Controller and Kubernetes Ingress to expose the application through an AWS Application Load Balancer.
- Implemented Prometheus and Grafana monitoring with Alertmanager-based alerting and email notifications.
- Integrated automated code-quality and container-security checks into the CI/CD workflow.
- Implemented Kubernetes and application validation to verify successful deployment and service availability.

---

## Repository Documentation

```text
docs/
├── architecture/
│   ├── Project_Architecture.png
│   ├── Project_Architecture_overview.jpg
│   └── Project_repo.png
│
└── screenshots/
    ├── aws/
    │   ├── actual application1.png
    │   ├── AWS Application Load Balancer Successfully Provisioned Through Kubernetes Ingress1.png
    │   ├── ec2_instances1.png
    │   ├── EKS Application Pods Running Successfully1.png
    │   ├── eks_cluster1.png
    │   ├── Kubernetes Service Successfully Created1.png
    │   └── load_balancer1.png
    │
    ├── ci-cd/
    │   ├── alertmanager.png
    │   ├── Alertmanager_alert.png
    │   ├── all_stages_Passed.png
    │   ├── Gmail_alert.png
    │   ├── Grafana_dashboard1.png
    │   ├── Grafana_firing_alert1.png
    │   ├── Prometheus_alert1.png
    │   ├── Prometheus_Grafana_connection1.png
    │   ├── Prometheus_query1.png
    │   └── Prometheus_svc_monitoring1.png
    │
    ├── docker/
    │   ├── added_test1.png
    │   ├── dockerfile_configuration1.png
    │   ├── dockerhub_image1.png
    │   ├── docker_image1.png
    │   └── test_pass1.png
    │
    ├── kubernetes/
    │   ├── 01_terraform_apply_complete.png
    │   ├── 02_kubernetes_nodes_ready.png
    │   ├── 03_kubernetes_cluster_info.png
    │   ├── 04_kubernetes_system_pods.png
    │   ├── 07_load_balancer_controller_iam_policy.png
    │   ├── 08_lb_controller_iam_serviceaccount.png
    │   ├── 09_lb_controller_serviceaccount.png
    │   └── eks_cluster1.png
    │
    ├── monitoring/
    │   ├── 10_prometheus_stack_installed1.png
    │   └── 11_observability_pods_running1.png
    │
    └── security/
        ├── SonarQube/
        │   ├── gitlab_pipeline_sucess1.png
        │   ├── sonarqube_analysis_history.png -1 .png
        │   ├── sonarqube_project_overview1 .png
        │   ├── sonarqube_quality_gate1.png
        │   └── sonarqube_security_issues.png -1.png
        │
        └── Trivy_image_scan/
            ├── Screenshot1.png
            └── trivy_image_scan_added1.png
```

---

## Project Status

This project demonstrates an end-to-end DevSecOps workflow integrating application testing, CI/CD automation, infrastructure as code, containerization, security scanning, Kubernetes deployment, AWS load balancing, monitoring, and alerting on Amazon EKS.
