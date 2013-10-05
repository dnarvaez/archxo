# Install on USB stick

Format the USB stick. For example

    sudo mkfs.ext4 -F /dev/sdb

Mount it

    sudo mount /dev/sdb /mnt

Unpack the roots

    cd /mnt
    sudo tar xfJ /home/dnarvaez/rootfs.tar.xz

Unmount the stick

    sudo umount /dev/sdb

Finally plug in the stick and start the XO.

# Build a rootfs

This will include only the packages which are essential to boot, configure
wifi and install packages.

    pacstrap -d /rootfs systemd systemd-sysvcompat \
        pacman netctl wpa_supplicant
