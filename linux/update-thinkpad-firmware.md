Copied from https://workaround.org/article/updating-the-bios-on-lenovo-laptops-from-linux-using-a-usb-flash-stick/

    apt-get install genisoimage

    geteltorito -o bios.img g2uj18us.iso

    dmesg | tail

    dd if=bios.img of=/dev/sdb bs=1M
