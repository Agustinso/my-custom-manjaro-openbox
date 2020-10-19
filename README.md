# Primera CLI
## 1. Instalar paquetes base 
`yay -Sy xf86-video-intel lib32-mesa xorg lightdm xf86-input-synaptics nushell openssh openbox pcmanfm udisks2 samba gvfs-smb manjaro-settings-samba gvfs obconf obkey engrampa nitrogen rofi obmenu3 python2 python2-pip python python-pip menumaker alsa pulseaudio pavucontrol ttf-cascadia-code code alsa-tools python-pywal xsel xsettingsd lxappearance scrot viewnior compton git xclip flattr gmrun lxrandr dunst termite speedtest-cli lxappearancw-obconf gotop tty-clock min firefox polybar ttf-unifont octave evince oblogout lightdm-webkit-theme-sequoia-git papirus-icon-theme ttf-hack fish tree htop jgmenu slop wmctrl quicktile lightdm-slick-greeter bluez bluedevil pulseaudio-modules-bt`

## 2. Configurar greeter
https://github.com/naueramant/lightdm-webkit-sequoia

"Enable the theme in your `/etc/lightdm/lightdm-webkit2-greeter.conf` Search for greeter section Set `webkit-theme` to `sequoia` "
Set seat in lightdm to `lightdm-webkit2-greeter`

## 3. Configurar sistema

```
sudo systemctl enable --now sshd
sudo systemctl enable lightdm
sudo localectl set-x11-keymap es es
```

## 4. Instalar temas

https://github.com/edisile/walbox
```
git clone https://github.com/edisile/walbox.git
cd walbox
./install.sh

chsh -s /usr/bin/fish agustin
curl -L https://get.oh-my.fish | fish

omf install pure
ln -s $OMF_PATH/themes/pure/conf.d/pure.fish ~/.config/fish/conf.d/pure.fish

quicktile
```

# autostart
```
picom -i 1 -e 1 --active-opacity 1 &
polybar example &
wal -R -n &
nitrogen --set-zoom-fill img/bg.jpg &
quicktile -d
xsettingsd &

```

# .zshrc

```
(cat ~/.cache/wal/sequences &)
. "~/.cache/wal/colors.sh"
```

# COnfg
```
bindsym XF86AudioRaiseVolume exec --no-startup-id pactl set-sink-volume @DEFAULT_SINK@ +10% && $refresh_i3status
bindsym XF86AudioLowerVolume exec --no-startup-id pactl set-sink-volume @DEFAULT_SINK@ -10% && $refresh_i3status
bindsym XF86AudioMute exec --no-startup-id pactl set-sink-mute @DEFAULT_SINK@ toggle && $refresh_i3status
bindsym XF86AudioMicMute exec --no-startup-id pactl set-source-mute @DEFAULT_SOURCE@ toggle && $refresh_i3status


# music control
bindsym XF86AudioNext exec mpc next
bindsym XF86AudioPrev exec mpc prev
bindsym XF86AudioPlay exec mpc toggle
bindsym XF86AudioStop exec mpc stop


```



# links
https://github.com/naueramant/lightdm-webkit-sequoia

https://aur.archlinux.org/packages/openbox-themes/

https://wiki.archlinux.org/index.php/Openbox_(Espa%C3%B1ol)

https://github.com/polybar/polybar/wiki

https://www.opencode.net/ju1464/Teja

https://github.com/edisile/walbox

https://wiki.archlinux.org/index.php/File_manager_functionality

https://wiki.archlinux.org/index.php/Dunst

