# Install arch

## set keyboard layout and font

By default it's a US layout.

To change:
1. list the available layout:
    > ls /usr/share/kbd/keymaps/--/-.map.gz (replace the - with asterisk)
2. select the layout:
    > loadkeys layoutFileWithoutExtension
    > ex: loadkeys fr-latin1 (french azerty layout)

If in need of a bigger font:
> setfont ter-132b (132 is the size, b == bold, n for normal)

List font with ls /usr/share/kbd/consolefonts

## Verify boot mode

Check if using UEFI or bios:

> cat /sys/firmware/efi/fw_platform_size

if return 64 or 32: UEFI 64bit or 32bit
if file does not exist: BIOS

Modern pc should be in UEFI

## Connect to wifi

1. iwctl
2. List the devices (ex: wlan0):
    > device list
3. If not on:
    > device {device} set-property Powered on
4.  Scan (it won't output anything):
    > station {device} scan
5. List the network:
    > station {device} get-networks
6. Connect:
    > station {device} connect {network name}
7. If it does not say wrong password after a few second, it's good
8. exit
9. Check with:
    > ping google.com

## Partition the disks

1. list available disk
    > fdisk -l
    Loop0 can be ignore

2. GPT or MBR table:
    1. older pc or BIOS: MBR (But GPT might be use if supported, which is better)
    2. recent or UEFI: GPT
 
#### Partition layout

For MBR, see wiki

For GPT table, the basic partition layout is:

| mount point   | partition | type                         | size            |
|---------------|-----------|------------------------------|-----------------|
| /boot or /efi | /dev/sda1 | EFI system partition         | 300mib min      |
| [swap]        | /dev/sda2 | Linux swap                   | 512mib min      |
| /             | /dev/sda3 | Linux (or Linux x86-64 root) | remaining space |

>Note for a nvme it would be nvme0n1, nvme0n2...

A separate /home partition can also be used. In that case allocate around 20gib (30 max) for the root
and give the rest to the home in sda4.

#### Partition the disk

Use fdisk with the desire disk:
> fdisk /dev/sda (or nvme0n, sdb...)

>!! When selecting the type, double check the number with `L`

1. Create a GPT table by typing `g`
2. Create the efi partition:
    1. Type `n` to create new partition
    2. Press enter if the default number is `1`
    3. Press enter to select the default first sector
    4. Enter +550M or the desired size for the efi part
    5. Once create, change the type by pressing `t` then `1` for efi
3. Create the swap partition:
    1. Type `n`, then enter if num is `2`, then enter for first sector
    2. For last sector enter +512M or the desired size
    3. Change the type by pressing `t`, check that the part 2 is selected
    4. Type `82` (or 19) for linux swap
4. Create the root partition:
    1. type `n`, then enter if num is `3`, then enter for first sector
    2. For last sector, press enter if you only want a root partition and no other, otherwise choose the size with +xG
    3. Change the type by pressing `t`, check that the part 3 is selected
    4. Type `83` (20) for Linux file system
5. Eventually create a home partition, same process as the root
5. Create additional partition if needed, then press `w` to save the changes

#### Format the partition

Each newly created partition must be formatted

For EFI:
> mkfs.fat -F32 /dev/efi_partition
> mkfs.fat -F32 /dev/sda1
 
For swap:
> mkswap /dev/swap_partition
> mkswap /dev/sda2

For the root partition and home:
> mkfs.ext4 /dev/root_partition
> mkfs.ext4 /dev/sda3

## Mount the file systems

For the root:
> mount /dev/root_partition /mnt

For the EFI boot:
- For Grub mount in: /mnt/boot/efi or /mnt/boot
- For Systemd-boot: /mnt/boot
> mount --mkdir /dev/efi_partition /mnt/boot/efi
or
> mount --mkdir /dev/efi_partition /mnt/boot
 
 

For swap (! it's not using mount):
> swapon /dev/swap_partition

For home:
> mount --mkdir /dev/home_partition /mnt/home

## Install the base packages

> pacstrap -K /mnt base linux linux-firmware

## Generate an fstab

It define how partition are mounted
> genfstab -U /mnt >> /mnt/etc/fstab

## Chroot into the new system

> arch-chroot /mnt

## Install needed packages

> pacman -S networkmanager neovim vim git sudo iwctl firefox kitty...

Enable networkmanager:
> systemctl enable NetworkManager

!! Check if a firmware is needed for the wifi card, 
check the name of the card: 
> lspci -k  (look for network controller)
then google it or look this [page](https://wiki.archlinux.org/title/Network_configuration/Wireless#Troubleshooting_drivers_and_firmware)

## Set the time zone

> ln -sf /usr/share/zoneinfo/Europe/Paris /etc/localtime
> hwclock --systohc

## Set localization

Edit /etc/locale.gen and uncomment the needed locales.
Uncomment `en_US.UTF-8 UTF-8`
and/or `fr_FR.UTF-8 UTF-8`

Then generate the locales file with:
> locale-gen

## Network configuration

Set the hostname by creating /etc/hostname file and typing the 
hostname in it.

>Note: this is not the username

## Root pasword

Set a root password with:
> passwd

## Add users

Create a user (-m -> create /home, -G -> group list)
> useradd -m -G wheel [username] 

Set password
> passwd [username]

Let user use sudo (sudo must be installed)
> usermod -aG wheel <username> (if you haven't had it in the user creation)
> visudo
> uncomment %wheel ALL=(ALL:ALL) ALL (don't uncomment the one that does not ask for passwd)

## Boot loader

#### Grub

In efi:
> pacman -S grub efibootmgr
> pacman -S amd-ucode // or intel-ucode
> grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=GRUB
> grub-mkconfig -o /boot/grub/grub.cfg

If it says: 'efibootmgr not found' -> pacman -S efibootmgr

Note: the amd-ucode is optional but better to install amd microcode. It
check for update for the cpu microcode (whatever that is).

#### Systemd-boot

> pacman -S efibootmgr
> pacman -S amd-ucode               // or intel-ucode
> bootctl --path=/boot install
> cd /boot/loader

 Edit the `entries` directory and `loader.conf` file:

Loader.conf:
- Uncomment the `timeout 3` if you want to add a delay before starting the system
- Enter `default   arch-*` (or modify the default entry if already one)

Entries:
- cd /entries
- create entry: `nvim arch.conf`

```markdown
title   Arch Linux
linux   /vmlinuz-linux
initrd  /amd-ucode.img                      or intel-ucode.img
initrd  /initramfs-linux.img
options root=PARTUUID=root-part-uid rw
```
To find the root partition uuid either:
- blkid /dev/root-partition (ex: blkid /dev/sda2)
- Or remove the options lines form the arch.conf file and enter in the console:
    > echo "options root=PARTUUID=$(blkid -s PARTUUID -o value /dev/sdX2) rw" >> /boot/loader/entries/arch.conf
    > Just replace sdX2 with the correct root partition


## Reboot

Exit the chroot with `exit`
It's better to umount all the partition with `umount -R /mnt`
Type `reboot` and remove the installation media


# After installing


## Setting up AUR

1. Install dependency
> sudo pacman -S base-devel (git)

```bash
git clone https://aur.archlinux.org/yay-git.git 
cd yay-git
sudo pacman -S fakeroot
makepkg -si


# install package like so:
yay -S packagename
```


## Setting up standard /home directories

```bash
sudo pacman -S xdg-user-dirs

xdg-users-dirs-update
```


## Installing Xorg

>Note: if you install a desktop environment, you might not have to install X11

1. sudo pacman -S xorg
2. sudo pacman -S xorg-server xorg-xinit xorg-twm xorg-xclock xterm3. install a wm or a desktop
3. create .xinitrc in ~
4. add line to exec the wm or desktop:
    > exec i3
5. startx

You can also install the necessary driver:
> sudo pacman -S xf86-video-amdgpu
> sudo pacman -S xf86-video-intel
Or nvidia 

## Installing a display manager

For sddm (should be the same for any dm):
1. sudo pacman -S sddm
2. sudo systemctl enable sddm.service


## Sound

Alsa should be installed by default. By default all channel are muted.
To unmute:

```bash
amixer sset Master unmute
$ amixer sset Speaker unmute
$ amixer sset Headphone unmute
```
To use alsamixer:
> sudo pacman -S alsa-utils

## Bluetooth

```bash
sudo pacman -S bluez bluez-utils
sudo systemctl enable bluetooth.service
sudo systemctl start bluetooth.service
```


## Networking security

See DNS security and setting up firewall in the arch wiki.

## Style gtk and qt

See wiki.
