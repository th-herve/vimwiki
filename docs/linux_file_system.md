# Linux file system

| /          | root, anchor of the filesystem      |
| /usr       | Unix System Ressource, system file  |
| /usr/bin   | executable                          |
| /usr/lib   | shared libraires used by programs   |
| /usr/share | programs ressources (icons, art...) |
| /etc       | System configuration                |
| /var       | Log, caches, etc                    |
| /home      | User owned data                     |
| /proc      | runtime process data                |
| /tmp       | temporary data storage              |

## File type

- `-` regular file
- `d` directory
- `l` sym link
- `p` named pipe
- `c` character device file (backed by a hardware device that produces or receives data streams, like microphone)
- `b` block device file (backed by device that stores and loads blocks of data, like hard drive)
- `s` unix socket (local network connection encapsulated in a file)

[source](https://www.youtube.com/watch?v=w7nQFk6bi_k&list=PL-ymxv0nOtqqQ4NR1JnbWoHNm0Q8EspO1)
