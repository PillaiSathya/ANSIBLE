# Ansible Learning – Basics

## Topics Covered
- Ansible installation (Ubuntu / WSL)
- Control node vs Managed node
- Inventory configuration (project-level)
- Ansible ping module
- Ad-hoc commands
- Package installation using Ansible
- Idempotency validation

## Commands Used

### Ping Test
```bash
ansible -i inventory test -m ping
```
Install Nginx
```
ansible -i inventory test -m apt -a "name=nginx state=present update_cache=yes" --become -K
```
Outcome

Successfully automated nginx installation

Verified idempotent behavior (changed: false)

# Ansible Playbook – Nginx Automation
📄 Playbook: nginx-hw-playbook.yml

Purpose:
Automate the installation and basic configuration of an Nginx web server using Ansible.

What the playbook does:

Installs the nginx package using the apt module

Ensures the nginx service is running and enabled on boot

Deploys a custom static HTML page to /var/www/html/index.html

Demonstrates Ansible idempotency by producing no changes on repeated runs

How to run the playbook:
ansible-playbook -i inventory nginx-hw-playbook.yml -K

## Idempotency Validation:

First run: required resources are created (changed=1)

Second run: no changes detected (changed=0)

Verification:
curl localhost
![Screenshot for the o/p of ansible-playbook](playbook_output.png)

### Outcome
 
Successfully automated Nginx installation and configuration

Deployed a static web page using Ansible

Verified idempotent behavior using playbooks

Gained hands-on experience with real-world Ansible automation concepts

💡 This repository reflects my practical learning journey with Ansible, focusing on clarity, correctness, and real-world usage.
