# ansible-macos-ohmyzsh
Ansible role to manage zsh and oh-my-zsh installations.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-ohmyzsh.svg)](https://travis-ci.org/feffi/ansible-macos-ohmyzsh) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-ohmyzsh/total.svg)](https://github.com/feffi/ansible-macos-ohmyzsh) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-ohmyzsh.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-ohmyzsh) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-ohmyzsh.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-ohmyzsh) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-ohmyzsh.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-ohmyzsh) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-ohmyzsh/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-ohmyzsh.git
  name: feffi.macos-ohmyzsh
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_ohmyzsh:
  # Set zsh as default shell
  default: true
  # Configure oh-my-zsh after install?
  configure: true
  config:
    theme: "agnoster"
    case_sensitive: false
    hyphen_insensitive: false
    disable_update_prompt: false
    disable_auto_update: false
    update_days: 13
    disable_ls_colors: false
    disable_auto_title: false
    disable_correction: false
    completion_waiting_dots: true
    disable_untracked_files_dirty: false
    custom: "$ZSH/custom"
    plugins: "git"
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_ohmyzsh:
          # Set zsh as default shell
          default: true
          # Configure oh-my-zsh after install?
          configure: true
          config:
            theme: "agnoster"
            case_sensitive: false
            hyphen_insensitive: false
            disable_update_prompt: false
            disable_auto_update: false
            update_days: 13
            disable_ls_colors: false
            disable_auto_title: false
            disable_correction: false
            completion_waiting_dots: true
            disable_untracked_files_dirty: false
            custom: "$ZSH/custom"
            plugins: "git"
      roles:
        - { role: feffi.macos-ohmyzsh }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-ohmyzsh,
            macos_ohmyzsh: {
              # Set zsh as default shell
              default: true,
              # Configure oh-my-zsh after install?
              configure: false,
              config: {
                theme: "agnoster",
                case_sensitive: false,
                hyphen_insensitive: false,
                disable_update_prompt: false,
                disable_auto_update: false,
                update_days: 13,
                disable_ls_colors: false,
                disable_auto_title: false,
                disable_correction: false,
                completion_waiting_dots: true,
                disable_untracked_files_dirty: false,
                custom: "$ZSH/custom",
                plugins: "git"
              }
            }
          }
```
