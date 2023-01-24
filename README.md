## Checkmk

Role to install checkmk-agent *the role only currently installs the agent* hosts still have to be configured in the checkmk webui


### Example playbook
```ymal
---

- name: Configure CheckMK
  hosts: all
  become: true
  become_method: sudo
  roles:
      - checkmk

```