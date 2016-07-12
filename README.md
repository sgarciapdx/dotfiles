# dotfiles
Quick and dirty dotfile repo for my convenience. This is for:
- [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh)
- [Spacemacs](https://github.com/syl20bnr/spacemacs)

Vim configs live [elsewhere](https://github.com/sgarciapdx/vim-config).

Required packages for i3 stuff:
```
i3 i3status dunst xbacklight network-manager-applet
```

Nice-to-haves:
```
arandr adobe-source-code-pro-fonts
```

To use:
```
git clone git@github.com:sgarciapdx/dotfiles.git
ln -s /path/to/repo/dotfile /path/to/home/dotfile
```

Notes:
`00-keyboard.conf` goes in /etc/X11/xorg.conf.d (root:root)
