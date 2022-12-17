web browser
===========

A role to install web browser focus on privacy/security like `brave` or `librewolf`.

Try to install with your system packager if possible, use [flatpak](https://www.flatpak.org/) in last resort.

Requirements
------------

Ansible >=2.10

Role Variables
--------------

- `web_browser_brave`
  - Default: `false`
- `web_browser_librewolf`
  - Default: `false`

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

To install the last [librewolf](https://librewolf.net/)

    - hosts: desktop
      collection:
        - szorfein.desktop
      roles:
         - { role: web_browser, web_browser_librewolf: true }

License
-------

GPLv3+
