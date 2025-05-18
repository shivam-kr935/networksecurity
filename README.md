# 🚀 Deployment Guide (AWS)

## 1. 🔐 Login to AWS Console
Start by logging into the AWS Management Console.

## 2. 👤 Create IAM User for Deployment
Create an IAM user with specific access permissions:

- **EC2 Access** – for virtual machines  
- **S3 Access** – for storing artifacts and models  
- **ECR Access** – for Docker image registry

### ✅ Attach the following IAM policies:
- `AmazonEC2ContainerRegistryFullAccess`  
- `AmazonEC2FullAccess`  
- `AmazonS3FullAccess`

## 3. 🪣 Create an S3 Bucket
- **Region:** ap-south-1  
- **Bucket Name:** `scania-sensor-pipeline`

## 4. 📦 Create an ECR Repository
- **ECR Repository URI:**  
  `566373416292.dkr.ecr.ap-south-1.amazonaws.com/sensor-fault`

## 5. 💻 EC2 Machine Setup
Create an EC2 instance with **Ubuntu**.

## 6. 🐳 Install Docker on EC2
SSH into your EC2 instance and run:

```bash
sudo apt-get update -y
sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker

7. 🧑‍💻 Configure EC2 as Self-Hosted Runner (GitHub Actions)
Go to GitHub → Your Repo → Settings → Actions → Runners

Click New self-hosted runner

Choose your OS and follow setup instructions

8. 🔑 Setup GitHub Secrets
Add these secrets in your GitHub repository settings:

AWS_ACCESS_KEY_ID: Your AWS access key

AWS_SECRET_ACCESS_KEY: Your AWS secret key

AWS_REGION: ap-south-1

AWS_ECR_LOGIN_URI: 566373416292.dkr.ecr.ap-south-1.amazonaws.com

ECR_REPOSITORY_NAME: sensor-fault

MONGO_DB_URL: Your MongoDB Atlas connection string

9. 🚀 Deployment Steps Summary
Build Docker Image of your project

Push Docker Image to ECR

Start EC2 Instance

Pull Docker Image from ECR on EC2

Run Docker Container on EC2

✅ Your application is now deployed on AWS using CI/CD and Docker!
