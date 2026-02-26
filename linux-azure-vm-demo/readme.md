Linux Basics & Azure Virtual Machine Demo App
Overview

This project documents my hands-on Linux fundamentals and Azure VM deployment experience. The goal is to gain practical skills in Linux command-line usage, cloud VM setup, SSH access, Node.js installation, repository management, and running a demo application.

Part A – Linux Basics (Local)
Commands Executed

Check current directory

pwd

Screenshot: Azure-linus-commands.png

Create directory and navigate into it

mkdir week1-practice
cd week1-practice

Create a notes file

echo "My first Cloud/DevOps session" > notes.txt

List files

ls -l

Screenshot: Azure ls-notes.png

View file content

cat notes.txt

Screenshot: Azure cat-notes.png

Part B – Azure Virtual Machine
Step 1: VM Creation

Resource Group: Eunice-DevOps-Journey

VM Name: unique-1

OS: Ubuntu 24.04 LTS

Size: Standard D2s v3 (2 vCPU, 8 GiB RAM)

Public IP: 4.231.98.170

SSH Key: eunice-key.pem

Screenshot: Azure-VM creation.png

Step 2: SSH Access

Command used:

ssh -i /c/Users/eunic/OneDrive/Desktop/Azure-DevOps/eunice-key.pem eunice@4.231.98.170

Outputs verified:

whoami
hostname
pwd
ls

Screenshot: Azure-ssh-key.png and Azure cat & ls.png

Step 3: Install Git and Node.js
sudo apt update
sudo apt install -y git curl
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs

Verify installation:

node -v
npm -v

Screenshot: Azure-nodes.png

Step 4: Clone Demo Repository
cd ~
git clone https://github.com/helloSanmi/velo-learn.git
cd velo-learn
ls
cat README.md

Screenshots:

ls inside repo: Azure-app.png

cat README.md: Azure cat & ls.png

Step 5: Run Demo Application (Optional)
npm install
npm run dev

Local access: http://localhost:3000/

Network access: http://<VM-public-IP>:3000/

If the site does not load: add inbound rule for port 3000 in Azure Networking

Screenshot: working app (optional) – Azure-app.png

Lessons Learned

SSH access requires correct username and file permissions (chmod 400 on PEM file)

Node.js and Git installation on Linux VM are straightforward but require sudo privileges

Repository cloning requires navigating to the correct directory

Running a demo app may require adjusting firewall rules or inbound network settings

Folder Structure
week-01/
  notes.md
  screenshots/
    Azure-linus-commands.png
    Azure ls-notes.png
    Azure cat-notes.png
    Azure-VM creation.png
    Azure-ssh-key.png
    Azure-nodes.png
    Azure-app.png
    Azure cat & ls.png

Author: Eunice Oluwatobi Osuagwuh
Focus: Cloud & DevOps hands-on experience with Linux, Azure VMs, and Node.js deployments