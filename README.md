# Terraform-AWS-VPC-Deployment-Project
I used terraform to create a VPC in AWS


<h2>Tools & Technologies</h2>

* Terraform

* Amazon Web Services

* Chocolatey

* Visual Studio Code

* Git Bash

* Windows PowerShell

<h2>📊Architecture Diagram<h2>

<p>Below is a high-level architecture of the deployed infrastructure:<</p>

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
<h2>🔍 Architecture Explanation</h2>

* The VPC serves as the isolated network environment

* The Internet Gateway enables communication between the VPC and the internet

* The CIDR block 10.0.0.0/16 provides a scalable IP range

<p>The design is intentionally minimal and extensible for future additions:</p>

* Subnets

* Route tables

* NAT Gateway

* Compute resources

<h2>📸 Screenshots</h2>
<img width="1578" height="641" alt="image" src="https://github.com/user-attachments/assets/63dcbcdf-924a-4fe1-9448-6bb0e8392615" />



<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/8a50ecdf-1033-4f05-a451-72eb98a9a17e" />

<h2>⚙️ Setup & Installation</h2>

* Install Terraform via Chocolatey

* choco install terraform -y


<h2>🔐 AWS Authentication</h2>

   aws configure

<h2>📁 Project Structure</h2>

terraform-vpc-project/
├── provider.tf
├── vpc.tf
├── internet_gateway.tf
├── .terraform/
├── .terraform.lock.hcl
├── .gitignore
└── README.md

<h2>🧾 Terraform Configuration</h2>

* Provider

    provider "aws" {
  
      region = "eu-west-1"
    }

* VPC

      resource "aws_vpc" "main_vpc" {
  
        cidr_block = "10.0.0.0/16"
      
        tags = {
          Name = "main-vpc"
        }
}

* Internet Gateway

      resource "aws_internet_gateway" "igw" {
        vpc_id = aws_vpc.main_vpc.id
      
        tags = {
          Name = "main-igw"
        }
      }

<h2>▶️ Deployment</h2>

* terraform init

* terraform plan

* terraform apply


<h2>📚 Key Learnings</h2>

* Terraform workflow and lifecycle

* AWS networking fundamentals

* Infrastructure as Code best practices


<h2>⚠️ Challenges</h2>

* Resolved installation issue with Chocolatey

* Understood environment configuration and PATH issues


<h2>🔮 Future Improvements</h2>

* Subnets (public/private)

* Route tables

* NAT Gateway

* Kubernetes (EKS) integration

<h2>👤 Author</h2>

Blessing Taiwo

Cloud & DevOps Enthusiast

https://www.linkedin.com/in/blessing-umanu-taiwo-mgeoson-21a23b78/
