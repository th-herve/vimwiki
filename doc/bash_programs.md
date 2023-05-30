# Bash program

## tar

Combine and compress (or decompress) multiple file.  
Compress a directory/file(s) with: `tar -zcvf tarName.tar.gz file1orDir file2...`

- -c create a new archive
- -z compresses with gzip
- -v print the progress
- -f specify the name of the tar.gz

View the content of a tar.gz file with: `tar -ztvf tarName.tar.gz`.  
Extract the content with: `tar -xzvf file.tar.gz`
Extract and specify a dir with -C: `tar -xzvf my.tar.gz -C /home/backups/`

## xev

Display information about the key type.

## amixer/alsamixer

Control the volume with command or with gui (alsamixer).

ex:

```bash
// reducee volume
$ amixer -c 1 sset PCM 5%-

// up volume
$ amixer -c 1 sset PCM 5%+
```

## playerctl

Control media from command line.

>playerctl previous, playerctrl next, playerctl --player=spotify play-pause

## Timeshift

Backup https://doc.ubuntu-fr.org/timeshift
