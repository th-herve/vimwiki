# Install arch

TODO Add more info on creating separate /home partition

## set keyboard layout and font

see wiki

## Verify boot mode

Check if using UEFI or bios:

> cat /sys/firmware/efi/fw_platform_size

if return 64 or 32: UEFI 64bit or 32bit
if file does not exist: BIOS

Modern pc should be in UEFI

## Connect to wifi

see wiki

## Partition the disks

1. list available disk
    > fdisk -l
    Loop0 can be ignore

2. GPT or MBR table:
    1. older pc or BIOS: MBR (But GPT might be use if supported, which is better)
    2. recent or UEFI: GPT
 
### Partition layout

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

### Format the partition

Use fdisk with the desire disk:
> fdisk /dev/sda

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
5. Create additional partition if needed, then press `w` to save the changes

### Format the partition

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

### Mount the file systems

For the root:
> mount /dev/root_partition /mnt

For the EFI:
> mount --mkdir /dev/efi_partition /mnt/boot/efi

For swap (! it's not using mount):
> swapon /dev/swap_partition

### Install the essential packages

Install the base packages and the linux kernel 
> pacstrap -K /mnt base linux linux-firmware

## Configure the system

### Generate an fstab

It define how partition are mounted
> genfstab -U /mnt >> /mnt/etc/fstab

### Chroot into the new system

>arch-chroot /mnt

### Install essential packages

> pacman -S networkmanager neovim vim git sudo firefox kitty...

Enable networkmanager:
> systemctl enable NetworkManager

!! Check if a firmware is needed for the wifi card, check the name of the card: lspci -k then google it

### Set the time zone

> ln -sf /usr/share/zoneinfo/Europe/Paris /etc/localtime
> hwclock --systohc

### Set localization

Edit /etc/locale.gen and uncomment the needed locales.
Uncomment `en_US.UTF-8 UTF-8`
and/or `fr_FR.UTF-8 UTF-8`

Then generate the locales file with:
> locale-gen

### Network configuration

Set the hostname by creating /etc/hostname file and typing the 
hostname in it.

>Note: this is not the username

### Root pasword

Set a root password with:
> passwd

### Add users

Create a user (-m -> create /home, -G -> group list)
> useradd -m -G wheel [username] 

Set password
> passwd [username]

Let user use sudo (sudo must be installed)
> usermod -aG wheel <username> (if you haven't had it in the user creation)
> visudo
> uncomment %wheel ALL=(ALL:ALL) ALL (don't uncomment the one that does not ask for passwd)

### Boot loader

Install a boot loader, for grub (in UEFI):
> pacman -S grub efibootmgr
> pacman -S amd-ucode // or intel-ucode
> grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=GRUB
> grub-mkconfig -o /boot/grub/grub.cfg

If it says: 'efibootmgr not found' -> pacman -S efibootmgr

Note: the amd-ucode is optional but better to install amd microcode. It
check for update for the cpu microcode (whatever that is).

## Reboot

Exit the chroot with `exit`
It's better to umount all the partition with `umount -R /mnt`
Type `reboot` and remove the installation media




## Setting up AUR

1. Install dependency
> sudo pacman -S base-devel (git)



## Installing Xorg

>Note: if you install a desktop environment, you might not have to install X11

1. sudo pacman -S xorg-server xorg-xinit
2. install a wm or a desktop
3. create .xinitrc in ~
4. add line to exec the wm or desktop:
    > exec i3