1.25.0
======

+ Add a new role `web_browser`, can install Brave or LibreWolf.
+ Can use `dotfiles_gpu_driver='nouveau'` in the roles/dotfiles for old NVIDIA
  cards.
+ ALSA with the default config use the first audio card found. `cat
  /proc/asound/card*/id`.
+ Emacs was renamed `emacs_doom`, install [doomemacs](https://github.com/doomemacs/doomemacs)
