# Nautobot installation with Ansible
This repository contains a set of playbooks that installs everything that is needed for [Nautobot](https://github.com/nautobot/nautobot) on ubuntu.

This was tested on ubuntu 2204 lts.

Thanks to https://github.com/jtdub/ansible-install-nautobot for inspiration

# Prep

Install ansible-core and the postgresql community modules on the control node:

```
pip3 install ansible-core
ansible-galaxy collection install community.postgresql
```

# Installation

1. Modify the group_vars as desired
2. Run the ansible playbook playbooks/nautobot.yaml
3. Set up a superuser in nautobot:
    sudo -iu nautobot
    cd /opt/nautobot/venv/bin and run the following cmd:
    ```
    sudo -iu nautobot
    cd /opt/nautobot/venv/bin
    ./nautobot-server createsuperuser --config-path /opt/nautobot/nautobot_config.py
    ```
