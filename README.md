# galaxy-asdf
An Ansible Galaxy role for installing [asdf version manager](https://github.com/asdf-vm/asdf).

## Installation
Simply install via Ansible Galaxy:
```bash
ansible-galaxy install particledecay.asdf
```

## Usage
Include the role in your playbook and pass some vars:
```yaml
- name: Install binaries
  include_role:
    name: particledecay.asdf
  vars:
    asdf_plugins:
      - name: kubectl
        versions:
          - "1.16.0"
        global: "1.16.0"
      - name: helm
        versions:
          - "2.14.3"
          - "3.0.0-beta.3"
        global: "2.14.3"
```

You may also include a custom repository for a plugin not in the [official plugins](https://github.com/asdf-vm/asdf-plugins) list:
```yaml
- name: rke
  repository: "https://github.com/particledecay/asdf-rke.git"
  versions:
    - "v0.1.19"
  global: "v0.1.19"
```

