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
