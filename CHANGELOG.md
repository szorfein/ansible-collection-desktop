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
