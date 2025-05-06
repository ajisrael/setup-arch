# Arch Linux Setup Guide
__For `archlinux-2025.05.01-x86_64`__

## Installation
Get [iso](https://archlinux.org/download/) and follow [installation guide](https://wiki.archlinux.org/title/Installation_guide)

Burn ISO to bootable usb, and boot from usb

Select default installation option

Once installation terminal is loaded run `archinstall` to start installation guide

### `archinstall` steps

Select the region for the "Mirrors and repositories" as `United States`

For "Disk configuration" select to "Use a best-effort default partition layout" with `btrfs`.
Select `Yes` for BTRFS subvolumes with a default structure, and `Use compression` to keep the "copy on write" feature.

> Note:
>  - `btrfs` will allow us to more easily roll back system state due to "copy on write"
>  - `ext4` is more stable but older with not as many features

Set "Root password" and add a user making sure that they have `sudo` permission

Select `pipewire` for "Audio", this can be changed later

Leave the default linux kernel

Select `Use NetworkManager` for "Network configuration"

Set Timezone as desired

Select `Install`

### GNOME setup

After installation is complete select yes to `chroot` to install additional packages.
Now run the following command to install `GNOME`

```bash
pacman -S gnome
```

Hit `enter` to install all repositories, select `Y` (or just `enter`) to begin installation.

Now run the following command to enable the GDM (GNOME Display Manager) service:

```bash
sudo systemctl enable gdm.service
```

Once installation is complete, type `exit` to leave `chroot` session and then `sudo shutdown -h now` to shutdown the system.

### First Time Startup with VMWare

Now make sure that you enable 3DAcceleration by maxing out the vram and adjusting the display setting for the vm

## Setup
### Install Neofetch

```bash
sudo pacman -S neofetch
```

### Install Hyprland

These steps come from the [installation guide](https://wiki.hyprland.org/Getting-Started/Installation/)

```bash
sudo pacman -S hyprland
```

### Setup Hyprland

These steps come from the [master tutorial](https://wiki.hyprland.org/Getting-Started/Master-Tutorial/)

Install kitty

```bash
sudo pacman -S kitty
```
