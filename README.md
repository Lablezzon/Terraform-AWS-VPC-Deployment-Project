# Terraform-AWS-VPC-Deployment-Project
I used terraform to create a VPC in AWS


Tools & Technologies

Terraform

Amazon Web Services

Chocolatey

Visual Studio Code

Git Bash

Windows PowerShell

📊 Architecture Diagram

Below is a high-level architecture of the deployed infrastructure:

                Internet
                    │
            ┌───────▼────────┐
            │ Internet Gateway│
            └───────┬────────┘
                    │
            ┌───────▼────────┐
            │      VPC       │  (10.0.0.0/16)
            │                │
            │   (Future)     │
            │ ┌────────────┐ │
            │ │  Subnets   │ │
            │ │ (Public /  │ │
            │ │  Private)  │ │
            │ └────────────┘ │
            └────────────────┘
🔍 Architecture Explanation

The VPC serves as the isolated network environment

The Internet Gateway enables communication between the VPC and the internet

The CIDR block 10.0.0.0/16 provides a scalable IP range

The design is intentionally minimal and extensible for future additions:

Subnets

Route tables

NAT Gateway

Compute resources

📸 Screenshots


⚙️ Setup & Installation


Install Terraform via Chocolatey

choco install terraform -y


🔐 AWS Authentication

aws configure

📁 Project Structure

terraform-vpc-project/
├── provider.tf
├── vpc.tf
├── internet_gateway.tf
├── .terraform/
├── .terraform.lock.hcl
├── .gitignore
└── README.md

🧾 Terraform Configuration

Provider

provider "aws" {
  region = "eu-west-1"
}

VPC

resource "aws_vpc" "main_vpc" {
  cidr_block = "10.0.0.0/16"

  tags = {
    Name = "main-vpc"
  }
}
Internet Gateway

resource "aws_internet_gateway" "igw" {
  vpc_id = aws_vpc.main_vpc.id

  tags = {
    Name = "main-igw"
  }
}

▶️ Deployment

terraform init

terraform plan

terraform apply


📚 Key Learnings

Terraform workflow and lifecycle

AWS networking fundamentals

Infrastructure as Code best practices


⚠️ Challenges

Resolved installation issue with Chocolatey

Understood environment configuration and PATH issues


🔮 Future Improvements

Subnets (public/private)

Route tables

NAT Gateway

Kubernetes (EKS) integration

👤 Author

Blessing Taiwo
Cloud & DevOps Enthusiast
