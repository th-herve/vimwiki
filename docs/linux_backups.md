# How to backup in linux

Using rsync, allows to have incremental backup.

The basic command is:
> rsync -[flag] --exclude={"/exclude/pathOne/","/exclude/thisPathToo/"} [source/to/backup] [destination/to/store/backup]


Run this command to backup in `/mnt/SSD1/backups`
> time sudo rsync -aAXvz --delete --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} / /mnt/SSD1/backups/main_backup

Alternative with tar to create a compress backup
> time sudo tar -czvf /mnt/SSD1/backups/$backup_name.tar.gz --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} /


# Flag

| flag     | action                                                            |
|----------|-------------------------------------------------------------------|
| -a       | archive mode (preserves permissions, ownership...)                |
| -A       | Preserve ACLs (Access Control Lists)                              |
| -X       | Preserve extended attributes                                      |
| -v       | Verbose output (optional, for seeing progress)                    |
| -z       | Make it faster (compress the transfer, but `not` the final files) |
| --delete | Make an incremental backup,                                       |

If using rsync over ssh, you might want to use the `--numeric-ids` flag

## Restore file from backup

To restore with rsync, run the same command but reverse the source and destination:
> sudo rsync -aAXvz --delete --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} /mnt/SSD1/backups/main_backup /

If the system is not accessible, a backup can be made from a live preview of the os. In that case:

1. Create a usb key with the image of your os
2. Boot into it and select the live preview
3. Create a mount point to the device containing the backup 
    > mkdir /mnt/drive
4. Find the name of the device with `lsblk`
5. Mount the device with:
    > mount /dev/device/partition/name /mnt/drive 
6. Run the command:
    > sudo rsync -aAXvz --delete --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} /mnt/SSD1/backups/main_backup /
