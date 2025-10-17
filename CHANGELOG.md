# 1.56.0 - Oct. 2025

## Dotfiles

Trying globally to:

- Add install of foot (terminal)
- Remove vim and vifm.
- Add dunst for sway
- Remove dependencie to flatpak because https://flatkill.org/

### Archlinux

- Intel gen7 use mesa-amber instead of mesa package.
- Swayfx use scenefx0.4 from AUR
- Reaver download AUR snapshots now instead of using Ansible modules before executing playbook...

### Gentoo

- Correct package.use/dotfiles -- lack one `{% endif %}` in jinja template
- Intel gen7 use media-libs/mesa-amber instead of media-libs/mesa package.
- Correct use flag on librewolf-bin and other packages.

### Voidlinux

- Update package name 'Thunar' instead of 'thunar' (yep...)
- Update the install of Librewolf (used flatpack before), thanks https://github.com/index-0/librewolf-void
- Add StyLua to Neovim - Rubocop and Prettier not yet available.
- mesa-amber is not yet available [#48519](https://github.com/void-linux/void-packages/issues/48519)

# 1.50.0

- Add in role/dotfiles: Neovim
- Add in role/dotfiles: SwayFX
- Add in role/dotfiles: Wezterm
- Add in role/dotfiles: files-browser, install nnn, nemo or thunar.

## Dropped

- Making or removing stow link with Ansible.
- role/dotfiles: vifm

  # 1.44.0

- Add lxdm as display manager.

  # 1.43.0

### Dotfiles

- Update Awesome for last themes [focus](https://github.com/szorfein/dotfiles).
- Remove (a lot) code for download and extract files (ansible.builtin.get_url and
  ansible.builtin.unarchive). All this stuff is now made by
  [reaver](https://github.com/szorfein/reaver) before launching Ansible.
- Playbooks now execute faster.

### DM

- Correct lightdm - was locked because session-wrapper.
- Ensure dbus is started and enable for lightdm.
- Can configure lightdm to use extra backgrounds.

  # 1.36.0

* Correct ansible `get_url` by adding `use_netrc: false`
* New dependencie for ZSH - starship (https://starship.rs)
* Add vulkan with gpu_driver="intel" (gen 8 and more).
* Mask package >qtmultimedia-5.20 for Gentoo and SDDM.
* Doom emacs with more code linter.
* Correct the install with the `dotfiles_gpu_driver=intel` on Gentoo.

  # 1.30.0

- Can install Betterlockscreen (with i3lock-color).
- Configure Xorg keyboard.
- Use [DMIX](https://github.com/opensrc/alsa/blob/master/lib/md/Dmix.md) for ALSA to works with multiple audio source.
- Can use [reaver](https://github.com/szorfein/reaver), it's used to download
  all required files/archive, Ansible can almost work offline. If you use it, you have
  to manually define your collections, download them and tell to Ansible which archives to use.
- Rewrite debian-src.

  # 1.25.0

* Add a new role `web_browser`, can install Brave or LibreWolf.
* Can use `dotfiles_gpu_driver='nouveau'` in the roles/dotfiles for old NVIDIA
  cards.
* ALSA with the default config use the first audio card found. `cat
/proc/asound/card*/id`.
* Emacs was renamed `emacs_doom`, install [doomemacs](https://github.com/doomemacs/doomemacs)
