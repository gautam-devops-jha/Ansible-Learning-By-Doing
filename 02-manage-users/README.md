# Ansible User Management Project

This Ansible project facilitates user management tasks on remote machines. It includes playbooks for creating, modifying, and deleting user accounts, as well as configuring groups.

## Usage Instructions
### Prerequisites
Before using this project, ensure that you have:

- Ansible installed on your local machine.
- Access to target machines via SSH with appropriate privileges (e.g., root access or sudo permissions).

### Configuration

1. **Inventory Configuration:** Update the `hosts.ini` file with the IP addresses or hostnames of the target machines under the appropriate groups.  

Example :
```ini
[My-machines]
165.232.188.226
```

2. **Ansible Configuration:** Review and adjust the `ansible.cfg` file according to your requirements. This file contains default configurations for Ansible.


### Playbooks
This project includes the following playbooks:

1. **create-users.yml:** Creates user accounts with specified groups and SSH keys.

2. **create-user-without-home.yml:** Creates user accounts without creating home directories.

3. **delete-user.yml:** Deletes specified user accounts.



### Running Playbooks

To execute a playbook, use the ansible-playbook command followed by the playbook filename.

Example:  
```bash 
ansible-playbook create-users.yml
``` 

### Customization

Feel free to customize the playbooks (create-users.yml, create-user-without-home.yml, delete-user.yml) to meet your specific user management requirements. You can modify user parameters such as username, shell, groups, and SSH key settings.

