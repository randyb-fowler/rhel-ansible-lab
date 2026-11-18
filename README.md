# RHEL 9 + Ansible Home Lab

Three RHEL 9.9 servers in VMware Workstation, automated with Ansible.

| Host | IP | Role |
|---|---|---|
| control | 192.168.15.10 | Ansible control node |
| node1 | 192.168.15.11 | web group |
| node2 | 192.168.15.12 | db group |

## Playbooks
- **baseline.yml**: standard build (hosts file, admin tools, chrony, firewalld, users, login banner). Idempotent.
- **web.yml**: deploys Apache and opens the firewall on the web group.
- **patch.yml**: rolling patching, one server at a time, reboots only when needed.
- **dns.yml**: fleet-wide DNS change with nmcli, applied without dropping connections.
- **health.yml**: checks disk usage and critical services, fails loudly on problems.

## Skills practiced
RHEL install and cloning, nmcli networking, Red Hat subscription management,
SSH key auth, sudo, Ansible inventories, ad-hoc commands, playbooks, check mode, idempotence.
