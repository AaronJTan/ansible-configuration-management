# Ansible Configuration Management

This repository contains Ansible playbooks to configure my Ubuntu development machines and set up the UI.

As of now, the playbook configures the following tools:
- discord
- docker
- git
- intellij
- java
- python packages (pip3, venv)
- vim
- vlc
- vscode

## Prerequisites
- Ansible >= 2.14

## How to install Ansible
```
python3 -m pip install --user ansible
```

## Getting Started
### Set up SSH connections on remote nodes
Add your public SSH key to the `authorized_keys file` on each remote system.

### Building an Inventory
1. Create a copy of inventory-template.yaml and name it inventory.yaml:
```
cp inventory-template.yaml inventory.yaml
```

2. Build the inventory by adding the IP addesses or fully qualified domain names of the systems

## Running the playbooks
Run development playbook
```
ansible-playbook -K development.yaml
```

Run ui-customization playbook
```
ansible-playbook ui-customization.yaml
```

Run development playbook plays with specific tags <br />
See development.yaml for tags or run `ansible-playbook --list-tags development.yaml`
```
ansible-playbook -t [TAGS] development.yaml
```

## Other useful commands
Ping the managed nodes: 
```
ansible all -m ping
```

List all the managed nodes
```
ansible all --list-hosts
```

Gather facts about the managed nodes
```
ansible all -m gather_facts
```

List all available tags
```
ansible-playbook --list-tags development.yaml
```