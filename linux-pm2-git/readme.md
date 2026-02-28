# Linux Administration, PM2 Process Management, and Git Workflow
# Overview

This project focused on practical Linux system administration, application process management using PM2, and implementing a structured Git workflow.

# The objective was to:

Inspect and monitor system processes

Validate SSH service health and review authentication logs

Deploy and manage a Node.js application using PM2

Practice branching, committing, and Pull Request workflow in Git

---

# Part 1: Linux Processes, Services, and Logs

# Process Inspection:

To observe running processes and confirm SSH activity, the following commands were executed:

ps aux | head

ps aux | grep ssh

top

# Observations

The SSH daemon was actively running

Process ID remained stable

System uptime appeared normal

CPU and memory usage were within the expected range

---

# SSH Service Status Verification

The SSH service state was verified using:

systemctl status ssh

# Observations

SSH service is active and running

No warning messages present

Restart the counter at zero

This confirms that remote access to the VM is stable and operational.

---

# SSH Log Review

To review recent SSH activity

sudo journalctl -u ssh --since "30 minutes ago"
![](linux-pm2-git/screenshots/Azure-task2-4.png)

# Observations

Successful login recorded for azureuser

Multiple failed pre-authentication attempts from unknown IP addresses

Reinforces the importance of secure SSH key-based authentication

This step demonstrates monitoring and security awareness in cloud environments.

---

# Part 2: Application Management Using PM2

# PM2 Installation and Setup

PM2 was installed globally and used to manage the Velo Learn application.

# Commands executed:

sudo npm install -g pm2

pm2 start npm --name velo-learn -- run dev

pm2 list

pm2 logs velo-learn

pm2 startup

pm2 save

# Key Outcomes:

Application successfully launched under PM2

Process visible in PM2 list

Application logs accessible

Startup configuration enabled automatic restart after reboot

![](linux-pm2-git/screenshots/Azure-task2-6.png)
This confirms production style process management and resilience.

---

# Part 3: Git Workflow Practice

# Forking and Branching

The Velo Learn repository was forked to a personal GitHub account.

A feature branch was created

git checkout -b feature/add-name-to-readme

Updating README

Name was added under: Training student, "Eunice Osuagwuh"

-Commit and Push

-git add README.md

-git commit -m "Add my name to README"

-git push -u origin feature/add-name-to-readme

-Pull Request

-A Pull Request was opened from:

feature/add-name-to-readme → main

-The Pull Request was successfully merged into the forked repository.

This demonstrates understanding of collaborative Git workflows.

---

# Commands Executed During Practice

For documentation and reproducibility, all commands used during the session are listed below:

-ssh -i Hotey-key.pem azureuser@<VM-IP>

-ps aux | head

-ps aux | grep ssh

-top

-systemctl status ssh

-sudo journalctl -u ssh --since "30 minutes ago"

-chmod +x /home/azureuser/velo-learn/start_velo_learn.sh

-/home/azureuser/velo_learn/start_velo_learn.sh

-sudo npm install -g pm2

-pm2 start npm --name velo-learn -- run dev

-pm2 list

-pm2 logs velo-learn

-pm2 startup

-pm2 save

-git checkout -b feature/add-name-to-readme

-git add README.md

-git commit -m "Add my name to README"

-git push -u origin feature/add-name-to-readme

---

# Conclusion

This exercise reinforced:

Linux process inspection and log analysis

Service monitoring using systemctl

Secure SSH access awareness

Production-style application management using PM2

Structured Git branching and Pull Request workflow

This project strengthened practical DevOps foundations by combining system administration, application lifecycle management, and version control best practices.

# P.S: All proofs are in the screenshot folder.
