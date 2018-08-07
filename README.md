# dotfiles
Quick and dirty dotfile repo for my convenience. This is for:
- [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh)
- [Spacemacs](https://github.com/syl20bnr/spacemacs)
- [i3](https://i3wm.org)
- other miscellany

Vim configs live [elsewhere](https://github.com/sgarciapdx/vim-config).

## required packages for i3 stuff:
```
i3 i3status dunst xbacklight network-manager-applet
```

## nice-to-haves:
```
arandr adobe-source-code-pro-fonts redshift redshift-gtk pavucontrol
```

## to use:
```
git clone git@github.com:sgarciapdx/dotfiles.git
ln -s /path/to/repo/dotfile /path/to/home/dotfile
```

## notes:
- some i3 stuff is hardware-specific (batteries, etc.), YMMV
- ssh config requires OpenSSH 7.2 or newer for AddKeysToAgent
- `00-keyboard.conf` changes CapsLock to Ctrl and goes in /etc/X11/xorg.conf.d (root:root)
- `99-monitor-backlight.conf` sets up a generic backlight for use by xbacklight and goes in /etc/X11/xorg.conf.d (root:root)
