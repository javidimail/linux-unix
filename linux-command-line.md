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
Creat a file system: 
```bash
> mkfs.ext4 /dev/sdb
mke2fs 1.42.13 (17-May-2015)
Creating filesystem with 976754646 4k blocks and 244195328 inodes
Filesystem UUID: 6d69f90c-91ee-423e-92c3-e37cc8f90f7f
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
	4096000, 7962624, 11239424, 20480000, 23887872, 71663616, 78675968, 
	102400000, 214990848, 512000000, 550731776, 644972544

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information:            
done
```
mount again:
```bash
mount /dev/sdb temp-mount-folder/
mount: /dev/sdb mounted on /home/javidi/temp-mount-folder.
```

__How to install a cheap ($10-20, Temper Device USB) temperature sensor on a server__
```bash
git clone https://github.com/petervojtek/usb-thermometer.git
cd usb-thermometer/
make
sudo ./pcsensor
2018/04/13 08:08:46 Temperature 77.68F 25.38C
```
