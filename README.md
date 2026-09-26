# Debian-12-install-from-ISO-support
Providing additional functionality for diskless booting & installation of Debian Trixie via GNU GRUB. It is possible booting official Debian Installation (live) media diskless via GNU GRUB, but it is not possible installing the system via 
Debian Installer. This repository provides config and image files for this installation scenario. This solution was triggered by this bug report Mexit/MultiOS-USB#77 and adopted to MultiOS-USB as a 'one-click-solution', but is usable with any 
grub2 loopback setup.

# Features
- Filesystems: exfat, ext4
- Provide full debian boot menu
- Supported ISOs: Debian-DVD-1, Debian-netinst & all Debian-live images of Debian 12.15.0.

# Usage
Load provided 'scandev-12.15.0.gz' along with the main 'initrd.gz' of the installation media via grub loopback module. This adds necessary functionality for installing Debian 12.15.0 via debian 
installer. If you are using 'https://github.com/Mexit/MultiOS-USB', it is just a few steps:

0. Use MultiOS-USB partition on 'exfat' or 'ext4' filesystem.
1. Copy your Debian-12.15.0-iso files to 'ISOs' directory.
2. Create a directory for 'grub.cfg' files: '/MultiOS-USB/config_priv/debian-scandev'
3. Copy 'scandev-12.15.0.gz','live-12.15.0.gz', 'debian-12.15.0-amd64_d-i.cfg' and 'debian-12.15.0-amd64-d-i_live.cfg' there.
4. Reboot into 'MultiOS-USB' and start e.g. 'debian-12.15.0-amd64-DVD-1.iso [scandev]' entry.
5. Debian-installer will start same way as started from a usb-stick.
