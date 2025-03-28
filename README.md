# How to CI/CD

CI/CD means **Continuous Integration** and **Continuous Delivery/Deployment**. <br>
Developers can focus on the development.

This repository will introduce the ci/cd method using AWS and Github Actions

--- 

### Settings

#### 0. Check current `AWS region` 

#### 1. Create new **IAM user** 
- Generate Access Key while creting the user 
- Save both `Access Key ID` and `Secret Access Key` securely

#### 2. Create an **AWS ECR** (ECR : Elastic Container Registry)
- Record `repository name`

#### 3. Create **EC2 instance**
- OS : **Amazon Linux 2023**
- Security Group : Allow **HTTP**, **SSH**, **TCP(8000)**
- Generate and download `key pair(.pem)`
- Record `EC2 public IPv4 address`

#### 4. Add **IAM role** to EC2 instance
- Add **AmazonEC2ContainerRegistryReadOnly** policy


#### 5. Connect to EC2 instance and install docker
    ``` bash
    sudo dnf install -y docker

    sudo systemctl enable docker
    sudo systemctl start docker

    docker --version

    sudo usermod -aG docker ec2-user
    ```

#### 6. Go to Github repository, **Settings > Secrets and variables > Actions**
- Add the required secrets

#### 7. Deployed successfully, can test by visiting
> http://{public_ipv4}

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
