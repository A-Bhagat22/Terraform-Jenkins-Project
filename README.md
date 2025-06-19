# Terraform-Jenkins-Project
# 🚀 CI/CD Infrastructure: Jenkins Installation on AWS EC2 using Terraform

This project provisions an **AWS EC2 instance** using **Terraform**, automatically installs **Jenkins** via a `user_data` script, and exposes it over port 8080 — demonstrating Infrastructure as Code (IaC) and DevOps automation.

---

## 📦 Tech Stack

- Terraform
- AWS EC2 (Ubuntu)
- Jenkins
- Bash (for user data)
- Amazon Linux/Ubuntu AMI
- SSH / SCP

---

## 🧠 Project Overview

- EC2 instance is created using Terraform.
- Security group automatically opens port **8080** for Jenkins and **22** for SSH.
- A shell script runs automatically on launch using `user_data` to:
  - Install Java
  - Install Jenkins
  - Start Jenkins service
- After provisioning, Jenkins is available at:

👉 **[http://ec2-54-85-158-104.compute-1.amazonaws.com:8080](http://ec2-54-85-158-104.compute-1.amazonaws.com:8080)**

---

## 📂 Project Structure
terraform-jenkins-setup/
├── main.tf # Main Terraform config
├── variables.tf # Input variables
├── outputs.tf # Output variables (Jenkins URL)
├── jenkins_install.sh # Bash script for Jenkins installation
├── screenshots/ # Jenkins UI, terminal outputs
└── README.md


---

## 🔧 How to Run

### 1. Clone the Repo
```bash
git clone https://github.com/your-username/terraform-jenkins-setup.git
cd terraform-jenkins-setup


Initialize Terraform
terraform apply

Apply Infrastructure
terraform apply

Type yes to confirm
Outputs public IP and Jenkins URL

Access Jenkins
Go to the printed URL in browser (http://<ec2-public-ip>:8080)

Unlock using command:sudo cat /var/lib/jenkins/secrets/initialAdminPassword

| Port | Purpose |
| ---- | ------- |
| 22   | SSH     |
| 8080 | Jenkins |

📚 Learning Outcome
Infrastructure as Code with Terraform

Automating Jenkins installation via user_data

Real-world CI/CD environment provisioning

To Destroy Infra
terraform destroy
