dotfiles
========

A role to install dotfiles on your user home, original create to install [my own dotfiles](https://github.com/szorfein/dotfiles), it should be enought modular (with Stow) to other users.  

Requirements
------------

Ansible >=2.10

Role Variables
--------------

- `dotfiles_audio_backend`
  - Default: `undefined`
  - Description: Can be `alsa` or `pulseaudio`.
- `dotfiles_audio_alsa_stow_dir`
  - Default: `undefined`
  - Description: Config files for audio with Stow, relative to `dotfiles_stow_dir`, e.g: `alsa-sound`.
- `dotfiles_audio_pulseaudio_stow_dir`
  - Default: `undefined`
  - Description: Config files for audio with Stow, relative to `dotfiles_stow_dir`, e.g: `pulse-sound`.
- `dotfiles_awm`
  - Default: `false`
  - Description: Install awesome on Xorg (minimal).
- `dotfiles_awm_stow_dir`
  - Default: `undefined`
  - Description: Config files for awm with Stow, relative to `dotfiles_stow_dir`, e.g: `awm`.
- `dotfiles_awm_default_theme`
  - Default: `undefined`
  - Description: The string name of a theme to install with Stow if any, relative to `dotfiles_stow_dir_theme`.
- `dotfiles_emacs_doom`
  - Default: `false`
  - Description: Install [doom-emacs](https://github.com/doomemacs/doomemacs).
- `dotfiles_cache_dir`
  - Default: `~/.cache/dotfiles`
  - Description: Where playbook download archives before extract them.
- `dotfiles_external_font_dir`
  - Default: `~/.local/share/fonts`
  - Description: Fonts dir.
- `dotfiles_external_font_ad_hoc_items`
  - Default: `[]`
  - Description: A list of remote fonts to download directly, end by `.ttf`,
    `.otf`, etc.
- `dotfiles_external_font_zip_items`
  - Default: `[]`
  - Description: A list of remote `zip` font archive to download.
- `dotfiles_external_nerd_font_version`
  - Default: `2.2.2`
  - Description: Release version of the [Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases).
- `dotfiles_external_nerd_font_items`
  - Default: `[]`
  - Description: If need nerd font, add them. e.g: `- { name: Iosevka: hash: xxxxxx }`
- `dotfiles_gpu_driver`
  - Default: `''`
  - Description: For now, only support `intel_gen7` (ivybridge), `intel` (broadwell - Gen8 and more), `nouveau`, see the [doc](https://github.com/szorfein/ansible-collection-desktop/blob/main/roles/dotfiles/docs/GPU.md).
- `dotfiles_mpd`
  - Default: `false`
  - Description: Install and configure mpd with ncmpcpp and mpc.
- `dotfiles_mpd_music_dir`
  - Default: `~/musics`
  - Description: Music directory for mpd.
- `dotfiles_neomutt`
  - Default: `false`
  - Description: Install and configure neomutt.
- `dotfiles_neomutt_stow_dir`
  - Default: `undefined`
  - Description: Config files for neomutt with Stow, relative to `dotfiles_stow_dir`, e.g: `email`.
- `dotfiles_neomutt_accounts_dir`
  - Default: `[]`
  - Description: If need to create a directory relative to
    `dotfiles_neomutt_mail_dir`.
- `dotfiles_neomutt_mail_dir`
  - Default: `undefined`
  - Description: Directory for mails.
- `dotfiles_stow_dir`
  - Default: `undefined`
  - Description: If you need `GNU/Stow` to install config files, add the path here, e.g: `~/.dotfiles`.
- `dotfiles_stow_dir_theme`
  - Default: `undefined`
  - Description: If you use a special directory for install theme e.g: `~/dotfiles/themes`.
- `dotfiles_tmux`
  - Default: `false`
  - Description: Install tmux.
- `dotfiles_tmux_stow_dir`
  - Default: `undefined`
  - Description: Config files for tmux with Stow, relative to `dotfiles_stow_dir`, e.g: `tmux`.
- `dotfiles_vifm`
  - Default: `false`
  - Description: Install [vifm](https://github.com/vifm/vifm) with [vifmimg](https://github.com/cirala/vifmimg) and his dependencies.
- `dotfiles_vifm_stow_dir:`
  - Default: `undefined`
  - Description: Config files for vifm with Stow, relative to `dotfiles_stow_dir`, e.g: `vifm`.
- `dotfiles_vim`
  - Default: `false`
  - Description: Install and configure vim (not neovim).
- `dotfiles_vim_plugin_git_items:`
  - Default: `[]`
  - Description: A list of remote plugins from github to install with the native pack system, e.g: `- airblade/vim-gitgutter`
- `dotfiles_vim_plugin_tar_items:`
  - Default: `[]`
  - Description: A list of remote plugins from a `.tar.gz` archive to install with the native pack system.
- `dotfiles_vim_stow_dir:`
  - Default: `undefined`
  - Description: Config files for vim with Stow, relative to `dotfiles_stow_dir`, e.g: `vim`.
- `dotfiles_xorg_keymap`
  - Default: `en`
  - Description: Keymap used in Xorg, apply on the `Option "XkbLayout" "{{ dotfiles_xorg_keymap }}"`.
- `dotfiles_xorg_stow_dir`
  - Default: `undefined`
  - Description: Config files for X (.xinit, .xprofile, etc) with Stow, relative to `dotfiles_stow_dir`, e.g: `xorg`.
- `dotfiles_xst`
  - Default: `false`
  - Description: Build [xst](https://github.com/gnotclub/xst) or install it via your package manager if available.
- `dotfiles_zsh`
  - Default: `false`
  - Description: Use zsh as default shell.
- `dotfiles_zsh_theme_dir:`
  - Default: `undefined`
  - Description: Theme dir, for ohmyzsh, it look like `~/.oh-my-zsh/custom/themes`.
- `dotfiles_zsh_theme_items:`
  - Default: `[]`
  - Description: A list of remote themes to install `- { url: https://xxx, name: xxx }`, the `name:` will be installed in `dotfiles_zsh_theme_dir`.
- `dotfiles_zsh_link_items:`
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
        dotfiles_vim_plugin_git_items:
          - airblade/vim-gitgutter
          - Yggdroot/indentLine

You can show a complete example at
https://github.com/szorfein/dots/blob/ansible/ansible/group_vars/desktop.yml.tmpl
