# ans_role_config_dot_desktops

Add custom xxxx.desktop launcher files for terminal programs.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_dot_desktops.svg?label=release)](https://github.com/digimokan/ans_role_config_dot_desktops/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Add custom [Desktop Entry Files](https://specifications.freedesktop.org/desktop-entry-spec/desktop-entry-spec-latest.html)
  for terminal programs.

## Supported Operating Systems

* Ubuntu (via flatpak)
* Arch Linux
* FreeBSD

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_dot_desktops
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Add custom xxxx.desktop launcher files for terminal programs"
         ansible.builtin.include_role:
           name: ans_role_config_dot_desktops
           public: yes
         vars:
           start_term_emulator: "xterm"
           term_arg_exec_cmd: "-e "
           dot_desktop_launchers:
             - { cli: 'ranger_cd', name: 'ranger' }
   ```

## Role Options

See the role `defaults` files for main role vars listings:

  * [defaults](../defaults/main/)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_dot_desktops/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

