# === Manage Linux drive ===

`  Be carefull when working on drive 
`
When a storage device is plugged, it appear as its own file in `/dev/deviceName`

See the device connected and partition with `lsblk` or `sudo fdisk -l`.  
The device have standard name like so:
> Drive: sd(a|b|c...), ex: sde
> Partition: sd(a|b|c...)(1|2|3...) ex: sde4
> Tips: run those cmd before and after connecting a device to easily see which one it is.

sde          <- devicedisk
├─sde1       <- partition 1
└─sde2       <- partition 2

Target either a entire drive or a partition with their respective name:

```bash

ls -l /dev/sde

ls -l /dev/sde4

```

## == Using fdisk ==

In terminal, enter `sudo fdisk /dev/sde`

| key | action               |
|-----|----------------------|
| m   | help                 |
| p   | print drive info     |
| n   | create new partition |

### Create a partition with fdisk

1. `sudo fdisk /dev/sde`
2. type `p` to print info on the disk and see if there is partition already existing
3. press `n` to create a new partition
4. select the number, for example 1 would give sde4
5. for first sector, press enter unless you have reason to change it 
6. for last sector, either press enter to take the whole disk or specify a last to give it a certain amount of space. (type +100G for a 100gb partition, can be used with K,B,M,G...)
7. press `w` to write the change (`!!` if the change are overwriting data, it take effect once this step is entered)

The partition should be created. But `not` mounted `nor` formatted so not usable. (keep reading)

## == Format partition with mkfs ==

1. `sudo mkfs.<filesystem> /dev/sde4` 
> ex for Linux `sudo mkfs.ext4 /dev/sde4`

## == Mount a drive or partition manually ==

Assign a given location to access a drive. Mount either in:
- `/media/`: for temporary devices (usb key...)
- `/mnt/`: for more permanent devices (second ssd...)
> You can mount in any location but those two are conventional.

1. Open a terminal
2. Make a dir for mounting the drive, for exemple: `sudo mkdir /mnt/disk1`
3. Find the disk or partition with `lsblk`
4. Mount it: `sudo mount /dev/sde4 /mnt/disk1`


## == Unmount a drive or partition ==

Use `umount` and the location where the drive/partition is mounted.  
` ` it is `umount` and `not` unmount, no n after the u.


> `sudo umount /mnt/disk1`

## == Mount a drive automatically ==

`  Be extra carefull with fstab  `

`/etc/fstab` is a file used by the Linux system to automatically mount drive at startup.  
It is best to separate your entry lines from the one already existing with a line break.

To mount a partition add this line:
<deviceUUID> <locationToMount> <fileSystem> <option> <dumpNumber> <FileSystemCheckOrder>

- Device UUID: Unique identifier for the partition/device.Can be find with `sudo blkid`
- Location: The location where to mount the drive, generally you'll choose a directory in either `/mnt` or `/media` (` `make sure the dir is created)
- File system: The file system used by the partition (find with `sudo blkid`)
- Option: can be set to defaults (`with an s!`)
- Dump: just put `0`, it is old stuff.
- File check: number that determine the order this drive is checked in case of failure, putting `0` is probably best.

>ex: `UUID=e2a5fbf2-2f01-4d78-bfbd-7223874d89ea /mnt/dirName ext4 defaults 0 0`

### Step:

1. `sudo nvim /etc/fstab`
2. add the line for the corresponding device
    > `/dev/sde4 /mnt/dirName ext4 defaults 0 0`
3. Save the file

It is best to test:
1. Unmount the drive if it has been manually mounted with `umount /mnt/dirName`
2. run `sudo mount -a` it is gonna mount everything in the fstab file if not already mounted.
3. Check if the device is mounted with `mount | grep sde4` (if it has duplicate it's alright)

 
## == Check space usage with ncdu ==

Install ncdu: `sudo apt install ncdu`
Run: `sudo ncdu` or `sudo ncdu /`   
Add `-x` to exclude mounted drive.


[source](https://www.youtube.com/watch?v=2Z6ouBYfZr8)
[source fstab](https://www.youtube.com/watch?v=A7xH74o6kY0)
