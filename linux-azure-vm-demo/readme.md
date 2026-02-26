# Linux Basics & Azure Virtual Machine Demo App
Overview

This project documents my hands-on experience with Linux fundamentals and Azure VM deployment. The goal is to gain practical skills in Linux command-line usage, cloud VM setup, SSH access, Node.js installation, repository management, and running a demo application.

---

# Part A – Linux Basics (Local)
Commands Executed

# Check the current directory

pwd

![Linux Commands](/linux-azure-vm-demo/screenshot/azure-linux-commands.png)

---

# Create a directory and navigate into it

mkdir 

---

# List files

ls -l

![Linux Commands](/linux-azure-vm-demo/screenshot/azure-ls-notes.png)

---

# View file content

cat notes.txt

![Linux Commands](/linux-azure-vm-demo/screenshot/azure-cat-notes.png)

---

# Part B – Azure Virtual Machine
Step 1: VM Creation

Resource Group: Eunice-DevOps-Journey

VM Name: unique-1

OS: Ubuntu 24.04 LTS

Size: Standard D2s v3 (2 vCPU, 8 GiB RAM)

Public IP: 4.231.98.170

SSH Key: eunice-key.pem

![Linux Commands](/linux-azure-vm-demo/screenshot/Azure-VM-creation.png)

---

# Step 2: SSH Access

Command used:

ssh -i /c/Users/eunic/OneDrive/Desktop/Azure-DevOps/eunice-key.pem eunice@4.231.98.170

---

# Outputs verified:

whoami
hostname
pwd
ls

![Linux Commands](/linux-azure-vm-demo/screenshot/Azure-ssh-key.png)

![Linux Commands](/linux-azure-vm-demo/screenshot/Azure-cat-ls.png)

---

# Step 3: Install Git and Node.js
sudo apt update
sudo apt install -y git curl
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -

sudo apt install -y nodejs

---

# Verify installation:

node -v
npm -v

![Linux Commands](/linux-azure-vm-demo/screenshot/Azure-nodes.png)

---

# Step 4: Clone Demo Repository
cd ~
git clone https://github.com/helloSanmi/velo-learn.git
cd velo-learn
ls
cat README.md

![Linux Commands](/linux-azure-vm-demo/screenshot/Azure-cat-ls.png)

ls inside repo: Azure-app.png

cat README.md: Azure cat & ls.png

---

# Step 5: Run Demo Application (Optional)
npm install
npm run dev

Local access: http://localhost:3000/

Network access: http://<VM-public-IP>:3000/

If the site does not load, add an inbound rule for port 3000 in Azure Networking

![Linux Commands](/linux-azure-vm-demo/screenshot/Azure-app.png)

---

# Lessons Learned

SSH access requires the correct username and file permissions (chmod 400 on PEM file)

Node.js and Git installation on Linux VMs are straightforward but require sudo privileges

Repository cloning requires navigating to the correct directory

Running a demo app may require adjusting firewall rules or inbound network settings

---

Author: Eunice Oluwatobi Osuagwuh

Focus: Cloud & DevOps hands-on experience with Linux, Azure VMs, and Node.js deployments
