display_manager
===============

A role to install a display manager:

- [sddm](https://github.com/sddm/sddm)

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- `display_manager_sddm`
  - Default: `false`
  - Description: Install and configure sddm.
- `display_manager_background_dir`
  - Default: `''`
  - Description: Directory for background.
- `display_manager_background_items`
  - Default: `[]`
  - Description: A list of string url format `.tar.gz`.
- `display_manager_theme`
  - Default: `{}`

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

To install the last sddm theme [delicious-sddm-theme](https://github.com/stuomas/delicious-sddm-theme):

    - hosts: desktop
      roles:
         - szorfein.desktop.display_manager
      vars:
        display_manager_sddm: true
        display_manager_theme:
          url: 'https://github.com/stuomas/delicious-sddm-theme/archive/refs/heads/master.tar.gz'
          name: delicious
          sum: 20dda1a210cf736dc0454fca9c81edd564c87ebf66e022023071842759b7a960


Other nice sddm themes
----------------------

- [astronaut-theme](https://github.com/Keyitdev/sddm-astronaut-theme)
- [lubuntu-theme](https://github.com/the-zero885/lubuntu-sddm-theme)
- [anime](https://github.com/shinas101/Anime-sddm-theme)

License
-------

GPLv3+
