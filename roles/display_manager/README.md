display_manager
===============

A role to install a display manager:

- [sddm](https://github.com/sddm/sddm)
- lightdm
- lxdm

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- `dm_use`
  - Default: `''`
  - Description: The display manager to use, valid values are '', 'sddm', 'lxdm' or 'lightdm'.
  - Type: str
- `display_manager_background.name`
  - Default: `''`
  - Description: The name of the backgound image/video to load, e.g `black-wall.jpg`.
- `display_manager_background.sum`
  - Default: `''`
  - Description: The sha256sum for the archive.
- `dm_sddm_backgrounds`
  - Default: `[]`
  - Description: A list of archives to uncompress in dm_sddm_theme.background_dir `.tar.gz`.
- `display_manager_theme.name`
  - Default: `''`
  - Description: The name of the theme, used in the config file.
- `display_manager_theme.background_dir`
  - Default: `''`
  - Description: The background directory on theme, can be `Background`,
    `background`, `assert`, etc... depend on theme.
- `display_manager_theme.url`
  - Default: `''`
  - Description: The url for the theme to download `.tar.gz`.
- `dm_sddm_theme_customize`
  - Default: `[]`
  - Description: Modify the content of the `theme.conf` include in the theme.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

To install the last sddm theme [delicious-sddm-theme](https://github.com/stuomas/delicious-sddm-theme), change the background and customize the [theme.conf](https://github.com/stuomas/delicious-sddm-theme/blob/master/theme.conf):

    - hosts: desktop
      roles:
         - szorfein.desktop.display_manager
      vars:
        display_manager_sddm: true
        display_manager_background:
          url: 'https://github.com/szorfein/dm-bgs/archive/refs/heads/main.tar.gz'
          name: glitch.mp4
          sum: ccc1bdcb621d5a475d45da333b5dfa0e1f96a4b2b133fd850056ebf9edbc4f20
        display_manager_theme:
          url: 'https://github.com/stuomas/delicious-sddm-theme/archive/refs/heads/master.tar.gz'
          name: delicious
          background_dir: background
          sum: 20dda1a210cf736dc0454fca9c81edd564c87ebf66e022023071842759b7a960
        display_manager_theme_customize:
          - regexp: '^glowcolor='
            line: 'glowcolor=#BBA33393'
          - regexp: '^iconoverlay='
            line: 'iconoverlay=#FF000000'


Other nice sddm themes
----------------------

- [astronaut-theme](https://github.com/Keyitdev/sddm-astronaut-theme)
- [lubuntu-theme](https://github.com/the-zero885/lubuntu-sddm-theme)
- [anime](https://github.com/shinas101/Anime-sddm-theme)

Troubleshooting
---------------

Voidlinux need the package `mesa-dri`, it should depend of the graphic chipset.
