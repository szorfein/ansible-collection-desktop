dotfiles
========

A role to install dotfiles on your user home.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- `dotfiles_audio_backend`
  - Default: `undefined`
  - Description: Can be `alsa` or `pipewire`, if remain `undefined`, your distro may install the both by default or install `pulseaudio`.
- `dotfiles_audio_stow_dir`
  - Default: `undefined`
  - Description: Config files for audio with Stow, relative to `dotfiles_stow_dir`, e.g: `alsa-sound`.
- `dotfiles_mpd`
  - Default: `false`
- `dotfiles_mpd_music_dir`
  - Default: `~/musics`
  - Description: Music directory for mpd.
- `dotfiles_stow_dir`
  - Default: `undefined`
  - Description: If you need `GNU/Stow` to install config files, add the path here, e.g: `~/.dotfiles`.
- `dotfiles_vim`
  - Default: `false`
  - Description: Install and configure vim (not neovim).
- `dotfiles_vim_plugin_items:`
  - Default: `[]`
  - Description: A list of remote plugins from github to install with the native pack system, e.g: `- airblade/vim-gitgutter`
- `dotfiles_vim_stow_dir:`
  - Default: `undefined`
  - Description: Config files for vim with Stow, relative to `dotfiles_stow_dir`, e.g: `vim`.
- `dotfiles_zsh`
  - Default: `false`
  - Description: Use zsh as default shell.
- `dotfiles_zsh_plugin_items:`
  - Default: `[]`
  - Description: A list of remote plugins to install `- { src: https://xxx, dest: xxx }`
- `dotfiles_zsh_plugin_link_items:`
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
         - dotfiles
      vars:
        dotfiles_vim: true
        dotfiles_vim_plugin_items:
          - airblade/vim-gitgutter
          - Yggdroot/indentLine

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
