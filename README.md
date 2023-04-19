## Checkmk

Role to install Checkmk agent, the role only installs the agent and optionally configures a firewall (only supports iptables)

Dependacies

[Common role](https://gitlab.valhallaonline.info/valhallaonline/ansible-roles/common)

### Variables

- `checkmk_url` (Required) Define the checkmk server url
- `checkmk_version` (Required) Defines the version of the agent file. (Defaults to 2.0.0p19)
- `checkmk_instance_name` (Required) defines the checkmk instance name.
- `checkmk_firewall` (Required) defines if the role should configure the firewall or not. (Defaults to false)
- `check_mk_server_ip` (Optional) defines the server ip for the firewall rules (required if checkmk_firewall = true)
- `checkmk_agent_port` (optional) defines the agent port if not using the standard checkmk port. (defaults to 6556)

### Example Playbook

```yaml
- name: Install checkmk
  hosts: all
  become: true
  become_user: root
  roles:
    - role: checkmk
  vars:
    checkmk_url: checkmk.valhallaonline.info
    checkmk_version: 2.0.0p19
    checkmk_instance_name: cmk
```
