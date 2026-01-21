# Ragul-Capstone-Github
Ragul-Capstone-Github

🚀 Ragul-Capstone Project
End-to-End DevOps Pipeline for a Node.js Web Application
📌 Project Description

Ragul-Capstone is an end-to-end DevOps project that demonstrates how a web application can be automatically built, containerized, deployed, monitored, and maintained using modern DevOps tools and practices.

In this project, a simple Node.js web application is taken through a complete DevOps lifecycle.
Whenever a developer pushes code to GitHub, the entire process—from build to deployment—happens automatically without manual intervention.

This project reflects real-world DevOps workflows used in IT companies.

🎯 Project Objectives

The main objectives of this project are:

To store and manage application source code using GitHub
To automate build and deployment using Jenkins
To containerize the application using Docker
To deploy the application on AWS EC2
To monitor infrastructure and application health
To automate backups and maintenance tasks

🧰 Tech Stack Used
🔹 Source Control

Git

GitHub

🔹 CI/CD
Jenkins (installed on AWS EC2)

🔹 Application
Node.js Web Application (single container)

🔹 Containerization
Docker
Docker Hub

🔹 Cloud Infrastructure
AWS EC2 (Ubuntu)

🔹 Monitoring
Prometheus
Node Exporter
Grafana

🔹 Automation
Bash Shell Scripting
Cron Jobs

🏗️ Project Architecture (High-Level)

The project follows this workflow:

Developer pushes code to GitHub
Jenkins automatically triggers the pipeline
Jenkins installs dependencies and builds the application
Docker image is created and pushed to Docker Hub
Jenkins deploys the Docker container on AWS EC2
Prometheus collects system metrics
Grafana visualizes metrics and sends alerts
Cron jobs handle backups and cleanup tasks
⚙️ Setup Instructions (Run Locally)
🔹 Prerequisites

Make sure the following tools are installed on your system:

Git
Node.js
Docker

🔄 CI/CD Flow (Brief Explanation)

This project uses Jenkins Pipeline for Continuous Integration and Continuous Deployment.

CI/CD Flow:

Developer pushes code to GitHub
GitHub webhook notifies Jenkins
Jenkins pipeline starts automatically
Jenkins performs the following stages:
Checkout code
Install dependencies
Build Docker image
Push Docker image to Docker Hub
Deploy container on AWS EC2
Application becomes live without manual steps
Monitoring tools track system health
This ensures faster delivery, fewer errors, and consistent deployments.

📂 Repository Structure
Ragul-Capstone-Github/
│
├── app.js
├── package.json
├── Dockerfile
├── Jenkinsfile
├── README.md
└── scripts/
    └── backup.sh
