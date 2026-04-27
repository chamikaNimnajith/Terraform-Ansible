#  Terraform + Ansible Automation

This project — **terra-ansible-starter** — demonstrates how to use **Terraform** and **Ansible** together to provision and configure EC2 instances across multiple environments (**Dev**, **Stage**, and **Prod**).

Terraform handles the **infrastructure provisioning**, while Ansible automates **configuration management** — making this an ideal starter project for understanding how both tools collaborate in a real-world DevOps workflow.

---

## 🚀 Project Overview

### What this project does:
- Provisions **6 EC2 instances** (2 per environment: `dev`, `stage`, and `prod`).
- Creates a **security group** with rules for SSH (22) and HTTP (80).
- Uses **Ansible** to configure web servers on each instance.
- Deploys environment-specific `index.html` pages:
 

### Why it’s awesome:
- Full Infrastructure as Code (IaC) workflow.
- Dynamic inventory generation after `terraform apply`.
- Environment-based configuration using Ansible variables.
- Simple to extend to multi-region or autoscaling setups.

---

## 🧱 Project Structure

```

terra-ansible-starter/
├── terra-config/
│   ├── main.tf
│   ├── outputs.tf 
│   ├── variables.tf
│   └── provider.tf
│
├── ansible/
│   ├── ansible.cfg
│   ├── inventory/
│   ├── playbook.yml
│   └── roles/
│       └── webserver/
│           ├── tasks/
│           │   └── main.yml
│           └── files/
│               ├── index-dev.html
│               ├── index-stage.html
│               └── index-prod.html
│
├── scripts/
│   ├── generate_inventory.py
|
|
|--- deploy.sh
│
└── README.md

```

---

## ⚙️ Setup Instructions

### 1. Clone the repo
```bash
git clone https://github.com/chamikaNimnajith/Terraform-Ansible.git
cd Terraform-Ansible/terra-ansible-starter
```

### 2. Create SSH key for EC2 access

This project uses an SSH key named **appKey** to access your instances.

```bash
ssh-keygen -t rsa -b 4096 -f ~/.ssh/appKey
```


## 🧩 One-Click Deployment

To automate the full flow (Terraform → Inventory → Ansible):

```bash
bash deploy.sh
```

This script:

1. Runs `terraform apply`
2. Generates inventory
3. Executes the Ansible playbook
   All in one command ⚡️

---

## 🧰 Tools & Technologies

* **Terraform** — Infrastructure provisioning
* **Ansible** — Configuration management
* **AWS EC2** — Compute service
* **Nginx** — Web server
* **Python** — Used for generating inventory file

---


