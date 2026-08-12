# End-to-End DevSecOps CI/CD Pipeline on AWS EKS

An end-to-end DevSecOps project that automates application testing, code-quality analysis, containerization, vulnerability scanning, and deployment of a containerized application to Kubernetes running on Amazon EKS.

The project combines GitLab CI/CD, Docker, DockerHub, SonarQube, Trivy, Terraform, Kubernetes, Amazon EKS, Prometheus, Grafana, and Alertmanager into a single automated workflow.

---

## Project Architecture

The architecture below illustrates the overall flow from source code and CI/CD through containerization, security scanning, AWS infrastructure, Kubernetes deployment, and monitoring.

Terraform provisions the AWS infrastructure and Amazon EKS cluster used by the application. The GitLab CI/CD pipeline automates application testing, code-quality analysis, container image creation, security scanning, and deployment to Kubernetes.

The application is deployed to Kubernetes on Amazon EKS and exposed externally through Kubernetes Ingress and an AWS Application Load Balancer. Prometheus and Grafana provide monitoring and observability, while Alertmanager handles alerting and notification workflows.

<a href="docs/architecture/Project_Architecture.png">
<img src="docs/architecture/Project_Architecture.png" width="900" alt="End-to-End DevSecOps Project Architecture">
</a>

<a href="docs/architecture/Project_Architecture_overview.jpg">
<img src="docs/architecture/Project_Architecture_overview.jpg" width="900" alt="End-to-End DevSecOps Architecture Overview">
</a>

<a href="docs/architecture/Project_repo.png">
<img src="docs/architecture/Project_repo.png" width="900" alt="Project Repository Structure">
</a>

---

## CI/CD Pipeline

The GitLab CI/CD pipeline automates the application delivery process from testing through deployment to Amazon EKS.

Automated application tests validate functionality before the container image is built. SonarQube performs code-quality analysis, followed by Docker image creation and publication to DockerHub. Trivy then scans the container image for critical vulnerabilities before the application is deployed to Kubernetes running on Amazon EKS.

This pipeline provides a repeatable delivery workflow that integrates testing, code quality, containerization, security scanning, and deployment into a single automated process.

### Pipeline Stages

```text
GitLab
   |
   v
Unit Tests
   |
   v
SonarQube
   |
   v
Docker Build & Push
   |
   v
Trivy Image Scan
   |
   v
Deploy to Amazon EKS
```

### CI/CD Evidence

<a href="docs/screenshots/ci-cd/all_stages_Passed.png">
<img src="docs/screenshots/ci-cd/all_stages_Passed.png" width="900" alt="All CI/CD Pipeline Stages Passed">
</a>

<a href="docs/screenshots/ci-cd/alertmanager.png">
<img src="docs/screenshots/ci-cd/alertmanager.png" width="900" alt="Alertmanager">
</a>

<a href="docs/screenshots/ci-cd/Alertmanager_alert.png">
<img src="docs/screenshots/ci-cd/Alertmanager_alert.png" width="900" alt="Alertmanager Alert">
</a>

<a href="docs/screenshots/ci-cd/Gmail_alert.png">
<img src="docs/screenshots/ci-cd/Gmail_alert.png" width="900" alt="Gmail Alert Notification">
</a>

<a href="docs/screenshots/ci-cd/Prometheus_alert1.png">
<img src="docs/screenshots/ci-cd/Prometheus_alert1.png" width="900" alt="Prometheus Alert">
</a>

<a href="docs/screenshots/ci-cd/Prometheus_Grafana_connection1.png">
<img src="docs/screenshots/ci-cd/Prometheus_Grafana_connection1.png" width="900" alt="Prometheus Grafana Connection">
</a>

<a href="docs/screenshots/ci-cd/Prometheus_query1.png">
<img src="docs/screenshots/ci-cd/Prometheus_query1.png" width="900" alt="Prometheus Query">
</a>

<a href="docs/screenshots/ci-cd/Prometheus_svc_monitoring1.png">
<img src="docs/screenshots/ci-cd/Prometheus_svc_monitoring1.png" width="900" alt="Prometheus Service Monitoring">
</a>

<a href="docs/screenshots/ci-cd/Grafana_dashboard1.png">
<img src="docs/screenshots/ci-cd/Grafana_dashboard1.png" width="900" alt="Grafana Dashboard">
</a>

<a href="docs/screenshots/ci-cd/Grafana_firing_alert1.png">
<img src="docs/screenshots/ci-cd/Grafana_firing_alert1.png" width="900" alt="Grafana Firing Alert">
</a>

---

## Docker

The application is containerized with Docker and the resulting image is pushed to DockerHub.

The Docker workflow allows the same application image tested in CI/CD to be promoted through the security scanning and deployment stages.

<a href="docs/screenshots/docker/dockerfile_configuration1.png">
<img src="docs/screenshots/docker/dockerfile_configuration1.png" width="900" alt="Dockerfile Configuration">
</a>

<a href="docs/screenshots/docker/docker_image1.png">
<img src="docs/screenshots/docker/docker_image1.png" width="900" alt="Docker Image">
</a>

<a href="docs/screenshots/docker/dockerhub_image1.png">
<img src="docs/screenshots/docker/dockerhub_image1.png" width="900" alt="DockerHub Image">
</a>

<a href="docs/screenshots/docker/added_test1.png">
<img src="docs/screenshots/docker/added_test1.png" width="900" alt="Docker Application Test">
</a>

<a href="docs/screenshots/docker/test_pass1.png">
<img src="docs/screenshots/docker/test_pass1.png" width="900" alt="Docker Test Passed">
</a>

---

## Kubernetes and Amazon EKS

The application is deployed to Kubernetes running on Amazon EKS.

Terraform provisions the AWS infrastructure and EKS cluster, while Kubernetes manifests define the application deployment, services, ingress, and supporting resources.

### Kubernetes Evidence

<a href="docs/screenshots/kubernetes/01_terraform_apply_complete.png">
<img src="docs/screenshots/kubernetes/01_terraform_apply_complete.png" width="900" alt="Terraform Apply Completed">
</a>

<a href="docs/screenshots/kubernetes/02_kubernetes_nodes_ready.png">
<img src="docs/screenshots/kubernetes/02_kubernetes_nodes_ready.png" width="900" alt="Kubernetes Nodes Ready">
</a>

<a href="docs/screenshots/kubernetes/03_kubernetes_cluster_info.png">
<img src="docs/screenshots/kubernetes/03_kubernetes_cluster_info.png" width="900" alt="Kubernetes Cluster Information">
</a>

<a href="docs/screenshots/kubernetes/04_kubernetes_system_pods.png">
<img src="docs/screenshots/kubernetes/04_kubernetes_system_pods.png" width="900" alt="Kubernetes System Pods">
</a>

<a href="docs/screenshots/kubernetes/07_load_balancer_controller_iam_policy.png">
<img src="docs/screenshots/kubernetes/07_load_balancer_controller_iam_policy.png" width="900" alt="AWS Load Balancer Controller IAM Policy">
</a>

<a href="docs/screenshots/kubernetes/08_lb_controller_iam_serviceaccount.png">
<img src="docs/screenshots/kubernetes/08_lb_controller_iam_serviceaccount.png" width="900" alt="Load Balancer Controller IAM Service Account">
</a>

<a href="docs/screenshots/kubernetes/09_lb_controller_serviceaccount.png">
<img src="docs/screenshots/kubernetes/09_lb_controller_serviceaccount.png" width="900" alt="Load Balancer Controller Service Account">
</a>

<a href="docs/screenshots/kubernetes/eks_cluster1.png">
<img src="docs/screenshots/kubernetes/eks_cluster1.png" width="900" alt="Amazon EKS Cluster">
</a>

---

## AWS Infrastructure

The application infrastructure is hosted on AWS using Amazon EKS and supporting AWS resources.

Kubernetes Ingress is used to expose the application through an AWS Application Load Balancer.

<a href="docs/screenshots/aws/eks_cluster1.png">
<img src="docs/screenshots/aws/eks_cluster1.png" width="900" alt="Amazon EKS Cluster">
</a>

<a href="docs/screenshots/aws/ec2_instances1.png">
<img src="docs/screenshots/aws/ec2_instances1.png" width="900" alt="AWS EC2 Instances">
</a>

<a href="docs/screenshots/aws/EKS Application Pods Running Successfully1.png">
<img src="docs/screenshots/aws/EKS%20Application%20Pods%20Running%20Successfully1.png" width="900" alt="EKS Application Pods Running Successfully">
</a>

<a href="docs/screenshots/aws/Kubernetes Service Successfully Created1.png">
<img src="docs/screenshots/aws/Kubernetes%20Service%20Successfully%20Created1.png" width="900" alt="Kubernetes Service Successfully Created">
</a>

<a href="docs/screenshots/aws/load_balancer1.png">
<img src="docs/screenshots/aws/load_balancer1.png" width="900" alt="AWS Load Balancer">
</a>

<a href="docs/screenshots/aws/AWS Application Load Balancer Successfully Provisioned Through Kubernetes Ingress1.png">
<img src="docs/screenshots/aws/AWS%20Application%20Load%20Balancer%20Successfully%20Provisioned%20Through%20Kubernetes%20Ingress1.png" width="900" alt="AWS Application Load Balancer Provisioned Through Kubernetes Ingress">
</a>

<a href="docs/screenshots/aws/actual application1.png">
<img src="docs/screenshots/aws/actual%20application1.png" width="900" alt="Deployed Application">
</a>

---

## DevSecOps Security

Security is integrated into the CI/CD workflow rather than being treated as a separate step after deployment.

The pipeline uses SonarQube for automated code-quality and security analysis and Trivy to scan the container image for known vulnerabilities before deployment.

### SonarQube

SonarQube is integrated into the CI/CD workflow for automated code-quality and security analysis.

<a href="docs/screenshots/security/SonarQube/gitlab_pipeline_sucess1.png">
<img src="docs/screenshots/security/SonarQube/gitlab_pipeline_sucess1.png" width="900" alt="GitLab Pipeline SonarQube Success">
</a>

<a href="docs/screenshots/security/SonarQube/sonarqube_analysis_history.png%20-1%20.png">
<img src="docs/screenshots/security/SonarQube/sonarqube_analysis_history.png%20-1%20.png" width="900" alt="SonarQube Analysis History">
</a>

<a href="docs/screenshots/security/SonarQube/sonarqube_project_overview1%20.png">
<img src="docs/screenshots/security/SonarQube/sonarqube_project_overview1%20.png" width="900" alt="SonarQube Project Overview">
</a>

<a href="docs/screenshots/security/SonarQube/sonarqube_quality_gate1.png">
<img src="docs/screenshots/security/SonarQube/sonarqube_quality_gate1.png" width="900" alt="SonarQube Quality Gate">
</a>

<a href="docs/screenshots/security/SonarQube/sonarqube_security_issues.png%20-1.png">
<img src="docs/screenshots/security/SonarQube/sonarqube_security_issues.png%20-1.png" width="900" alt="SonarQube Security Issues">
</a>

### Trivy

Trivy scans the container image for known vulnerabilities before deployment.

<a href="docs/screenshots/security/Trivy_image_scan/Screenshot1.png">
<img src="docs/screenshots/security/Trivy_image_scan/Screenshot1.png" width="900" alt="Trivy Image Scan">
</a>

<a href="docs/screenshots/security/Trivy_image_scan/trivy_image_scan_added1.png">
<img src="docs/screenshots/security/Trivy_image_scan/trivy_image_scan_added1.png" width="900" alt="Trivy Container Image Scan">
</a>

---

## Monitoring and Observability

The project uses Prometheus, Grafana, and Alertmanager for monitoring and alerting.

The monitoring workflow is:

```text
Application / Kubernetes
          |
          v
      Prometheus
          |
          +----> Grafana
          |
          v
     Alertmanager
          |
          v
   Email Notification
```

### Monitoring Evidence

<a href="docs/screenshots/monitoring/10_prometheus_stack_installed1.png">
<img src="docs/screenshots/monitoring/10_prometheus_stack_installed1.png" width="900" alt="Prometheus Stack Installed">
</a>

<a href="docs/screenshots/monitoring/11_observability_pods_running1.png">
<img src="docs/screenshots/monitoring/11_observability_pods_running1.png" width="900" alt="Observability Pods Running">
</a>

---

## Application Validation

The deployed application is tested after deployment to verify that the application is successfully running in the Kubernetes environment.

---

## Infrastructure as Code

Terraform is used to provision the AWS infrastructure supporting the EKS deployment.

```text
Terraform
   |
   v
AWS Infrastructure
   |
   v
Amazon EKS
   |
   v
Kubernetes
```

---

## Technologies

| Area           | Technologies                      |
| -------------- | --------------------------------- |
| Cloud          | AWS, Amazon EKS                   |
| Infrastructure | Terraform                         |
| CI/CD          | GitLab, GitLab CI/CD              |
| Containers     | Docker, DockerHub                 |
| Security       | SonarQube, Trivy                  |
| Orchestration  | Kubernetes                        |
| Monitoring     | Prometheus, Grafana, Alertmanager |
| Application    | Node.js                           |

---

## DevOps Concepts Demonstrated

- Infrastructure as Code
- Continuous Integration and Continuous Delivery
- Containerization
- Kubernetes orchestration
- AWS/EKS deployment
- Automated application testing
- Static code analysis
- Container vulnerability scanning
- Application health checks
- Metrics collection
- Monitoring dashboards
- Alerting and email notifications
- Security integrated into CI/CD

---

## Repository Structure

```text
end_to_end_devsecops_project/
├── K8s/
│   ├── app/
│   └── monitoring/
├── docs/
│   ├── architecture/
│   └── screenshots/
├── public/
├── src/
├── terraform/
├── test/
├── .dockerignore
├── .gitignore
├── Dockerfile
├── package.json
├── package-lock.json
└── README.md
```

---

## Repository Documentation

All supporting screenshots and architecture documentation are stored under the `docs/` directory.

```text
docs/
├── architecture/
└── screenshots/
    ├── aws/
    ├── ci-cd/
    ├── docker/
    ├── kubernetes/
    ├── monitoring/
    └── security/
```

The screenshots displayed above are clickable and can be opened at their original resolution.

---

## Resume Version

**End-to-End DevSecOps CI/CD Pipeline — AWS EKS**

- Built an end-to-end GitLab CI/CD pipeline automating unit testing, SonarQube code analysis, Docker image build/push, Trivy vulnerability scanning, and deployment to Amazon EKS.
- Provisioned AWS infrastructure using Terraform and deployed a containerized Node.js application to Kubernetes with external load-balanced access.
- Implemented Prometheus and Grafana monitoring with Alertmanager-based alerting and email notifications.
- Integrated automated code-quality and container-security checks into the CI/CD workflow to provide security controls before deployment.
- Implemented application health and metrics endpoints to support Kubernetes validation and Prometheus-based observability.

---

## Project Highlights

This project demonstrates an end-to-end DevSecOps workflow covering:

```text
Source Code
    |
    v
Automated Testing
    |
    v
SonarQube Code Quality
    |
    v
Docker Build & DockerHub
    |
    v
Trivy Security Scan
    |
    v
Terraform / AWS Infrastructure
    |
    v
Amazon EKS
    |
    v
Kubernetes
    |
    v
Application Load Balancer
    |
    v
Prometheus + Grafana
    |
    v
Alertmanager
    |
    v
Email Notifications
```
