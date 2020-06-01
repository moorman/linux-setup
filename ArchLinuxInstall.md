# Arch Linux Install
## installatie
1. timedatectl set-ntp true
1. formateren
    1. lsblk
    1. cfdisk ....
    1. mkfs ....
1. mount ....
1. optional: mirrorlist
1. pacstrap /mnt base base-devel linux linux-firmware 
    vim networkmanager grub zsh man-db man-pages
    xorg-xinit xorg-server xfce4 xfce4-pulseaudio-plugin pulseaudio pavucontrol
    firefox git code
    * Optioneel: pulseaudio-alsa pulseaudio-jack pulseaudio-bluetooth neovim 
## configuratie
1. genfstab -U /mnt >> /mnt/etc/fstab
1. arch-chroot /mnt 
1. vim /etc/hostname /etc/locale.gen /etc/locale.conf
1. locale-gen
1. ln -sf /usr/var/zoneinfo/.... /etc/localtime
1. systemctl enable NetworkManager
## GRUB
1. grub-install /dev/sda
1. grub-mkconfig -o /boot/grub/crub.cfg
## gebruikers
1. passwd
1. useradd -mg wheel ed
1. passwd ed
1. vim /etc/sudoers
## reboot
1. exit
1. umount -R /nmt
1. reboot now
## desktop
1. login as user 
1. echo 'exec startxfce4' > .xinit
1. startx
