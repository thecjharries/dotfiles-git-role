# `dotfiles-git-role`

[![Build Status](https://travis-ci.org/thecjharries/dotfiles-git-role.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-git-role)

## Requirements

Fedora 27 is recommended.

## Role Variables

Defaults are below.

    owning_user: "{{ ansible_user }}"
    owning_group: "{{ ansible_user }}"
    root_dir: "/home/{{ ansible_user }}"
    config_dir: "{{ root_dir }}/.config"

Additionally, these `vars` are set:

    needed_packages:
      - git
      - gitflow

Finally, these variables must be set:

    user_name
    user_email

## Dependencies

```yml
---
- src: git+https://github.com/thecjharries/dotfiles-common-software-role.git
- src: git+https://github.com/thecjharries/dotfiles-package-installer-role.git
- src: git+https://github.com/thecjharries/dotfiles-generic-template-role.git
```

## Example Playbook

    - hosts: all

    roles:
      - role: dotfiles-git-role
        user_name: "Rick James"
        user_email: "something@clever.com"

## License

ISC
