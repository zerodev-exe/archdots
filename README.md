# HyprV3
This is V3 of the Hyprland install script

collection of dot config files for hyprland with a simple install script for a fresh Arch linux with yay

You can grab the config files and install packages by hand with this commnad

Do this ONLY if you need Nvidia support (do this first)
```
yay -S linux-headers nvidia-dkms qt5-wayland qt5ct libva libva-nvidia-driver-git

Add modules: nvidia nvidia_modeset nvidia_uvm nvidia_drm to /etc/mkinitcpio.conf

Generate new image: sudo mkinitcpio --config /etc/mkinitcpio.conf --generate /boot/initramfs-custom.img

Add/create the following: options nvidia-drm modeset=1 in /etc/modprobe.d/nvidia.conf

reboot!
```

Now install the below for Hyprland

```
yay -S hyprland kitty jq mako waybar-hyprland swww swaylock-effects \
wofi wlogout xdg-desktop-portal-hyprland swappy grim slurp thunar \
polkit-gnome python-requests pamixer pavucontrol brightnessctl bluez \
bluez-utils blueman network-manager-applet gvfs thunar-archive-plugin \
file-roller btop pacman-contrib starship ttf-jetbrains-mono-nerd \
noto-fonts-emoji lxappearance xfce4-settings sddm-git sddm-sugar-candy-git 
```

Or you can use the attached script "set-hypr" to install everything for you.

PS: I took everything from [SolDoesTech repo](https://github.com/SolDoesTech/HyprV3)

## Wifi

#### Inside of the arch ISO

```bash
station wlan0 scan
station wlan0 get-networks
station wlan0 connect <wifiname>
station wlan0 show
```

#### Inside of the installed version of arch if you are using NetworkManager

```
nmcli r wifi on
nmcli d wifi list
nmcli d wifi connect <wifiname> password <password>
```
