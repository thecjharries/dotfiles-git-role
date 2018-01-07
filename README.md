# `dotfiles-role-git`
# `dotfiles-role-git`

[![Build Status](https://travis-ci.org/thecjharries/dotfiles-role-git.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-role-git)
[![Build Status](https://travis-ci.org/thecjharries/dotfiles-role-git.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-role-git)

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
- src: git+https://github.com/thecjharries/dotfiles-role-common-software.git
- src: git+https://github.com/thecjharries/dotfiles-role-common-software.git
- src: git+https://github.com/thecjharries/dotfiles-role-package-installer.git
- src: git+https://github.com/thecjharries/dotfiles-role-package-installer.git
- src: git+https://github.com/thecjharries/dotfiles-role-generic-template.git
- src: git+https://github.com/thecjharries/dotfiles-role-generic-template.git
```

## Example Playbook

    - hosts: all

    roles:
      - role: dotfiles-role-git
      - role: dotfiles-role-git
        user_name: "Rick James"
        user_email: "something@clever.com"

## License

ISC
