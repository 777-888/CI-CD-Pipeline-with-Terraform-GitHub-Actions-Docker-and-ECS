# 📦 CI/CD Pipeline with Terraform, GitHub Actions, Docker, and ECS
## 🧠 Overview

This project demonstrates a complete CI/CD pipeline to deploy a containerized application on AWS using:

GitHub Actions for automation
Terraform for Infrastructure as Code
ECR for Docker image storage
ECS (Fargate) for container orchestration
EC2-based self-hosted runner to build and push Docker images
RDS as a backend database
S3 to manage assets or config files
## 📐 Architecture Diagram
(Include a PNG or draw.io diagram showing GitHub → Terraform → AWS Infrastructure)

## 🚀 Features
🔁 Full GitHub Actions CI/CD pipeline
🏗️ Terraform-managed infrastructure
🐳 Docker build & ECR push from EC2 self-hosted runner
📦 ECS Fargate service deployment
🔐 Secrets managed through GitHub
🧹 Auto cleanup with Terraform destroy
## ⚙️ Technologies Used
Tool	Purpose
Terraform	Define and provision infrastructure
GitHub Actions	Automate CI/CD workflow
Docker	Containerize the application
Amazon ECR	Store and manage container images
Amazon ECS	Run containers
Amazon EC2	Host self-managed GitHub runner
Amazon RDS	Store backend data
Amazon S3	Store zipped app & .env files
## 🛠️ How It Works
Push to main triggers the pipeline.
configure_aws_credentials job sets up credentials.
deploy_aws_infrastructure runs terraform apply to provision:
VPC, ECS, EC2 runner, ECR, RDS, and S3.
start_runner launches EC2 instance with a GitHub runner.
create_ecr_repository creates ECR repo if it doesn't exist.
build_and_push_image:
Builds Docker image from zipped app repo
Pushes image to ECR
ECS uses the image to run the app.
Outputs like domain, database endpoint, and image name are printed and used in later steps.
## 🧪 Example Outputs
Terraform Apply Complete!
Outputs:
image_name = "rentzone-app"
domain_name = "rentzone.com"
rds_endpoint = "dev-rds-db.****.rds.amazonaws.com"


## 💬 Credits
Created by Tristan Jones | LinkedIn

