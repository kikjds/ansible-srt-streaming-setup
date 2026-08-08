# ansible-srt-streaming-setup

Minimal set of Ansible playbooks to deploy a simple SRT streaming environment.

## About this project
- Automates installation and configuration of servers and services required for SRT stream delivery.
- Includes playbooks to install packages and prepare/configure the environment.

## Requirements
- Ansible 2.9+ (newer versions recommended)
- SSH access to the hosts listed in inventory.ini

## Quick start
1. Adjust the inventory: inventory.ini
2. Review variables in [group_vars/all.yaml](group_vars/all.yaml)
3. Run the main playbook:

```bash
ansible-playbook -i inventory.ini playbooks/main.yaml
```

## Minimal SRT streaming
- Ingest (send): srt://url:8282/?streamid=live/stream/<name>
- Receive: srt://url:8282/live/stream/<name>
- The server listens on port 8282; clients connect to the appropriate URI using the stream name.
- Streaming stats: http://url:8181/stats
