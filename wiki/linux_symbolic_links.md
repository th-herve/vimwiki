# Linux symbolic links

Symbolic links or symlink, link one object to another. Like a shortcut on windows.

Use `ln -s <full-path-file/dir-to-link> <path-to-link-location>` to create a symlink

Ex: create a link to test.txt on the desktop:
> ln -s /home/Document/test.txt /home/Desktop
>` `Use the full path, not ~/

In `ls -l`, sysLink are represented like so:
> `l`rwxrwxrwx 1 user date `test.txt -> /home/Document/test.txt`

## Soft and hard links

(by chat gpt)

A symbolic link, often referred to as a "symlink," is a type of soft link. It is a special file that acts as a pointer to another file or directory. Symlinks can be created using the ln -s command in Linux. When you access a symlink, the operating system resolves the link and follows the path to the target file or directory. Symlinks are essentially shortcuts or symbolic references.

On the other hand, hard links are created using the ln command without the -s option. Hard links create additional directory entries that point to the same underlying inode as the original file. Each hard link to a file is essentially equivalent, and there is no distinction between the original file and its hard links. Deleting the original file or any of its hard links does not affect the others, as they all reference the same file data.

In a Linux file system, each file and directory has its own unique inode. An inode contains metadata about the file or directory, such as ownership, permissions, timestamps, and pointers to the actual data blocks on the disk. Inodes are identified by inode numbers, which are unique within a specific file system.

When you create a soft link (symlink), a new inode is created for the link itself. This new inode holds the symlink's metadata and the path to the target file or directory. It has its own unique inode number.

In contrast, when you create a hard link, the same inode as the original file is used. Both the original file and the hard link(s) share the same inode number since they are essentially multiple names (directory entries) pointing to the same underlying data.

It's important to note that hard links cannot be moved to a different mount point or file system because inode numbers are specific to a particular file system. If you attempt to move a hard link to another file system, it effectively becomes a symbolic link pointing to a non-existing file. On the other hand, soft links can point to files or directories on different mount points or file systems.

To summarize, soft links (symlinks) are symbolic references or shortcuts to other files or directories, while hard links create additional directory entries pointing to the same underlying file data.
