# CI/CD Pipeline with Terraform, GitHub Actions, Docker, and ECS

## Overview

This project demonstrates a full-scale CI/CD pipeline that deploys a containerized application to AWS using:

- **Terraform** for infrastructure provisioning  
- **GitHub Actions** for automation and orchestration  
- **Docker** for containerization  
- **Amazon ECS (Fargate)** for container orchestration  
- **Amazon ECR** to store Docker images  
- **Amazon RDS** for the application database  
- **Amazon S3** for hosting zipped application and environment files  
- **EC2 self-hosted runner** to securely build and push Docker images  

---

## 📏 Architecture Diagram

coming soon

---

## ⚙️ Technologies Used

| Tool           | Purpose                                      |
|----------------|----------------------------------------------|
| Terraform      | Define and manage AWS infrastructure         |
| GitHub Actions | CI/CD pipeline automation                    |
| Docker         | Containerize the application                 |
| Amazon ECS     | Host containerized application               |
| Amazon ECR     | Store and retrieve Docker images             |
| Amazon RDS     | Manage relational database                   |
| Amazon S3      | Store zipped application assets & .env files |
| Amazon EC2     | Host a self-hosted GitHub Actions runner     |

---

## 🚀 Pipeline Workflow

1. **Push to `main`** triggers the GitHub Actions pipeline  
2. `configure_aws_credentials`: Authenticates using AWS credentials  
3. `deploy_aws_infrastructure`: Provisions infrastructure using Terraform  
4. `start_runner`: Starts a self-hosted EC2 GitHub Actions runner  
5. `create_ecr_repository`: Checks/creates the ECR repository  
6. `build_and_push_image`:  
   - Builds Docker image  
   - Pushes it to ECR  
7. ECS deploys the new image automatically  

---

## 📚 Folder Structure

```bash
.
├── .github/
│   └── workflows/
│       └── deploy_pipeline.yml
├── iac/
│   └── *.tf (Terraform files for AWS infrastructure)
├── screenshots/
│   └── architecture-diagram.png
├── Dockerfile
└── README.md


✅ Outputs

image_name       = "rentzone-app"
domain_name      = "rentzone.com"
rds_endpoint     = "dev-rds-db.xxxxx.rds.amazonaws.com"
image_tag        = "latest"
🤝 Collaboration

Contributions are welcome! Please fork the repo and submit a pull request if you'd like to improve this project or add new features.

🙌 Credits

Created by Tristan Jones

LinkedIn
GitHub
🤖 Future Improvements

Add automated teardown job
Use AWS CodePipeline for additional stages
Add Slack notification integration for CI status
📃 License

This project is licensed under the MIT License.
