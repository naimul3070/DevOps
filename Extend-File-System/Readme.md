## Extend File System

### show the file system disk space
    df -h
	
### Display details about block devices
    lsblk
	
### Logical volume information	
    lvs
	
### physical volume check	
    pvs
    pvscan
    pvdisplay
	
### physical volume create	(/dev/sdb--- check default sdb directory)
    pvcreate /dev/sdb
	
### volume group extend	
    vgextend ubuntu-vg /dev/sdb
	
### File formate checking	
    df -Th
	
### File formating 	
    mkfs.ext4 /dev/sdb
	
### Logical volume extend	
    lvextend -L +8G /dev/mapper/ubuntu--vg-ubuntu--lv
	
### Remove volume group( vgreduce - Remove physical volume(s) from a volume group)	
    vgreduce ubuntu-vg --removemissing
