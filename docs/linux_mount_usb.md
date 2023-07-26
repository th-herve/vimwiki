# Linux mount/unmount usb

Using `udisks2` (sudo pacman -S udisks2).

1. Identify the usb drive name:
    1. run lsblk
    2. plug the usb and run lsblk again
    3. Note the data partition of the usb (ex: sda1, NOT sda)
2. mount the partition

```bash
udisksctl mount -b /dev/sdxn
```
Find the drive's data in `/run/media/$USER/$DEVICE`

1. Eject the drive

```bash
# Unmount
udisksctl unmount -b /dev/sdxn

# Power off the drive
udisksctl power-off -b /dev/sdxn
```

[source](https://www.ejmastnak.com/tutorials/arch/usb/)
