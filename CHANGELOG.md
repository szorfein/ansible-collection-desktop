+ Add Neovim
+ Add Wezterm
+ Add SwayFX

## Dropped

- Making or removing stow link with Ansible.

1.44.0
======

- Add lxdm as display manager.

1.43.0
======

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

1.36.0
======

+ Correct ansible `get_url` by adding `use_netrc: false`
+ New dependencie for ZSH - starship (https://starship.rs)
+ Add vulkan with gpu_driver="intel" (gen 8 and more).
+ Mask package >qtmultimedia-5.20 for Gentoo and SDDM.
+ Doom emacs with more code linter.
+ Correct the install with the `dotfiles_gpu_driver=intel` on Gentoo.

1.30.0
======

* Can install Betterlockscreen (with i3lock-color).
* Configure Xorg keyboard.
* Use [DMIX](https://github.com/opensrc/alsa/blob/master/lib/md/Dmix.md) for ALSA to works with multiple audio source.
* Can use [reaver](https://github.com/szorfein/reaver), it's used to download
  all required files/archive, Ansible can almost work offline. If you use it, you have
  to manually define your collections, download them and tell to Ansible which archives to use.
* Rewrite debian-src.

1.25.0
======

+ Add a new role `web_browser`, can install Brave or LibreWolf.
+ Can use `dotfiles_gpu_driver='nouveau'` in the roles/dotfiles for old NVIDIA
  cards.
+ ALSA with the default config use the first audio card found. `cat
  /proc/asound/card*/id`.
+ Emacs was renamed `emacs_doom`, install [doomemacs](https://github.com/doomemacs/doomemacs)
