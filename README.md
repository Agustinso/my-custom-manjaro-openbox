# Primera CLI
## 1. Instalar paquetes base 
`yay -Sy xf86-video-intel lib32-mesa xorg xorg-xinit xf86-input-synaptics nushell openssh openbox pcmanfm udisks2 samba gvfs-smb manjaro-settings-samba gvfs obconf obkey engrampa nitrogen rofi obmenu3 python2 python2-pip python python-pip menumaker alsa pulseaudio pavucontrol ttf-cascadia-code code alsa-tools python-pywal xclip xsettingsd lxappearance scrot viewnior compton git xclip flattr gmrun lxrandr dunst termite speedtest-cli lxappearancw-obconf gotop tty-clock min firefox polybar ttf-unifont octave evince oblogout papirus-icon-theme ttf-hack fish tree htop jgmenu slop wmctrl quicktile bluez blueman pulseaudio-modules-bt gpointing-device-settings micro snapd awk qt5ct lxinput udiskie betterlockscreen xautolock thermald tlpui-git tlp vlc ttf-ubuntu-font-family`


## 3. Configurar sistema

```
sudo systemctl enable --now sshd
sudo localectl set-x11-keymap es es

sudo usermod -a -G tty agustin
sudo usermod -a -G uucp agustin
systemctl enable betterlockscreen@$USER
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

mkdir ~/.config/rofi
echo '@import "~/.cache/wal/colors-rofi-dark.rasi"' >> ~/.config/rofi/rofi.config

mkdir ~/.config/dunst
sudo cp /usr/share/dunst/dunstrc /home/user/.config/dunst/dunstrc
sudo chown user:user /home/user/.config/dunst/dunstrc
```

# autostart
```
picom -i 1 -e 1 --active-opacity 1 &
polybar example &
wal -R -n &
nitrogen --set-zoom-fill img/bg.jpg &
quicktile -d
xsettingsd &
pcmanfm -d &
blueman-applet &
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

bindsym Print --release exec "scrot /tmp/screenshot-$(date +%F_%T).png -e 'xclip -selection c -t image/png < $f'"
bindsym $mod+Print exec scrot ~/Pictures/scrot/%Y-%m-%d-%T-screenshot.png -e 'notify-send "Pantalla capturada en $f"'
bindsym --release $mod+Shift+Print exec scrot /tmp/screenshot.png -s -e 'xclip -selection c -t image/png < $f'


```

https://github.com/mateosss/matter#quick-start


# links
https://github.com/naueramant/lightdm-webkit-sequoia

https://aur.archlinux.org/packages/openbox-themes/

https://wiki.archlinux.org/index.php/Openbox_(Espa%C3%B1ol)

https://github.com/polybar/polybar/wiki

https://www.opencode.net/ju1464/Teja

https://github.com/edisile/walbox

https://wiki.archlinux.org/index.php/File_manager_functionality

https://wiki.archlinux.org/index.php/Dunst

