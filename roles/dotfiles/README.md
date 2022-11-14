dotfiles
========

A role to install dotfiles on your user home.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- `dotfiles_shell`
  - Default: `false`
  - Description: Install and configure default shell for user.
- `dotfiles_shell_pkgname`
  - Default: `zsh`
- `dotfiles_shell_path`
  - Default: `/usr/bin/zsh`
- `dotfiles_shell_plugin_items:`
  - Default: `[]`
  - Description: A list of remote plugins to install `- { src: https://xxx, dest: xxx }`
- `dotfiles_shell_plugin_link_items:`
  - Default: `[]`
  - Description: A list of links to create if need `- { src: xxx, dest: xxx }`

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: desktop
      collections:
        - szorfein.desktop
      roles:
         - { role: dotfiles, dotfiles_shell_pkgname: dash }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
