__advanced rsync__

1. rsync specific files & their folder:
```bash
rsync -avz --include=*/ --include='*myfilenameishere*' 
--exclude=* --prune-empty-dirs * /media/javidi/data/Dropbox/kotted-analysis/
```

__get rid of dead jobs that are still on qstat__

2. Force kill all jobs of a user after cluster shut down:
```bash
qselect -u javidi | xargs qdel -p
```

__How to mount a brand new flash drive/hard drive__
```bash
> lsblk

NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0 931.5G  0 disk 
├─sda1   8:1    0   512M  0 part 
├─sda2   8:2    0     1M  0 part 
├─sda3   8:3    0   7.9G  0 part [SWAP]
├─sda4   8:4    0 727.8G  0 part /media/javidi/data
└─sda5   8:5    0 195.3G  0 part /
sdb      8:16   0   3.7T  0 disk 
sr0     11:0    1  1024M  0 rom 

> mount /dev/sdb temp-mount-folder/
mount: wrong fs type, bad option, bad superblock on /dev/sdb,
       missing codepage or helper program, or other error

       In some cases useful info is found in syslog - try
       dmesg | tail or so.
```
