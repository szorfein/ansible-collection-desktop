dotfiles
========

A role to install dotfiles on your user home.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

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
- `dotfiles_stow_dir`
  - Default: `undefined`
  - Description: If you need `GNU/Stow` to install config files, add the path here, e.g: `~/.dotfiles`.
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

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
