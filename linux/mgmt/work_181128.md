# Mount HDD Disk on Ubuntu 16.04

After installation, I need to mount a new Hard Disk. So I followed the below instructions

## First, Check Hardware Disk

HDD Disk was physically mounted and detected by BIOS. So We don't need to install special driver to detect it. I thought that operator didn't wipe out the disk and format it. So I tried to notice the status of HDD Disk. 

**The status of HDD

```bash
# Check unmounted Disk
$> lshw -C disk 
# @TODO: (gbkim) After mounting it, The above command didn't work WHY?
$> lshw
# Make FileSystem (ext4)
$> mkfs -t ext4 /dev/sdb
```

## Last, Edit `/etc/fstab` and Let Mount it every boot time.

There are two methods to mount drive in your filesystem. 

- Edit `/etc/fstab`
  - Having the drive mounted automatically each time you boot the computer
- Manually `mount [filesystem] [device]` it
  - *Manually only when you need to use it*
  - `sudo mount /dev/sdb /data`

```bash 
# Create a Mount Point
$> mkdir /data
$> vim /etc/fstab
# ... Skipping .... 
/dev/sdb /data ext4 defaults 0 2
# Mount all drive
mount -a 
# Check Mount Point
lsblk
```
> CAUTION: Ubuntu guide recommend to use UUID instead. see the instructions here: https://help.ubuntu.com/community/UsingUUID

## Conclusion 

Today, I did mount a unused HDD Drive after installation was finished. 

But, there is a something to do. The thing is that I have to partition the mounted disk. :)

I see the https://help.ubuntu.com/community 

