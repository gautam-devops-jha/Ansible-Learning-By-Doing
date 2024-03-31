# Ansible Playbook and Role for Installing Basic Packages

This project contains an Ansible playbook and role for installing basic packages on remote machines.

## Contents

1. [Playbook and Role Information](#playbook-and-role-information)
2. [How to Run the Playbook](#how-to-run-the-playbook)
3. [How to Run the Role](#how-to-run-the-role)
4. [ansible.cfg File Explanation](#ansiblecfg-file-explanation)
5. [hosts.ini File Explanation](#hostsini-file-explanation)

## Playbook and Role Information

- **Playbook Name**: `install-software.yml`
- **Role Name**: `install-pkgs`
- **Entry Points**:
  - `install-software.yml`: This playbook can be run directly and does not include any role. It installs basic packages directly.
  - `run-role.yml`: This playbook includes the role `install-pkgs`, which installs basic packages.


## How to Run the Playbook

To run the playbook, use the following command:

```bash
ansible-playbook -i hosts.ini install-software.yml
``` 

Ensure you have the correct inventory file (`hosts.ini`) configured with your target hosts.

## How to Run the Role
 If you want to run just the role independently, you can use the following command:

```bash 
ansible-playbook -i hosts.ini run-role.yml
```
Again ensure you have the correct inventory file (`hosts.ini`) configured with your target hosts.

## ansible.cfg File Explanation

The ansible.cfg file contains configuration settings for Ansible:

**`host_key_checking`:** Disables SSH host key checking to avoid interactive prompts when connecting to new hosts.  

**`remote_user`:** Sets the remote user to 'root' (or you can set it to the user you machine is able to ssh with.) for all connections.

**`ansible_python_interpreter`:** Specifies the Python interpreter path to use on the remote machine.

**`become`:** Enables privilege escalation for tasks that require root access.  

**`become_method`:** Specifies the method for privilege escalation, which is set to 'sudo'.  

**`deprecation_warnings`:** Disables deprecation warnings to suppress unnecessary output.  

These settings provide defaults for Ansible to use during playbook/role execution.

## hosts.ini File Explanation

The ``hosts.ini`` file is the inventory file used by Ansible to define the hosts or groups of hosts on which the playbook will be executed. Each host entry in this file represents a target machine where the tasks defined in the playbook will run. 

Here's an example of how to create a simple ``hosts.ini`` file:

```ini 
[target-group]
192.168.1.100
192.168.1.101
```
Replace `target-group` and `IP addresses` with your actual IP addresses. 



