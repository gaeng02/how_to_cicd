# How to CI/CD

CI/CD means **Continuous Integration** and **Continuous Delivery/Deployment**. <br>
Developers can focus on the development.

This repository will introduce the ci/cd method using AWS and Github Actions

--- 

### SECRETS 
Repository -> Settings -> Security -> Secrets and variables -> Actions -> Secrets

| Name | Description | Example |
|:--|:--|:--|
| AWS_REGION            | your Region                           | ap-northeast-2 |
| AWS_ACCESS_KEY_ID     | IAM user Access Key ID                |   |
| AWS_SECRET_ACCESS_KEY | IAM user Secret Access Key            |   |
| ECR_REPOSITORY        | ECR repository name                   | cicd_ecr  |
| EC2_HOST              | public IP address of EC2 instance     |   |
| EC2_SSH_KEY           | private key for EC2 instance (`.pem`)  |   |
