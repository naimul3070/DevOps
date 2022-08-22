## External device temporary mount 

### Check usb has been support in linux 

    lsusb
     
![img_girl.jpg](https://user-images.githubusercontent.com/43438240/181905974-3f0de59a-fd30-4a35-9641-c15266ebe1df.png)

### Mount usb where you want . ( I need to mount /var/opt/mssql/data/ directory )

### Now check External device path 

    fdisk -l 
    
   ![image](https://user-images.githubusercontent.com/43438240/181906007-02b21f1f-62ed-45e5-b635-c9414f776745.png)
    
### External device information always get from  bottom of the line 
### Copye the drive path after fdisk command and mount where we want .

    mount /dev/sdb1 /var/opt/mssql/data/
    
### After press tempory mount will be done 

![image](https://user-images.githubusercontent.com/43438240/181906361-0bf59d7f-f0b9-4b62-a77a-27a793cee058.png)


### If you restart your device you have to mount again 


## un-mount [ check the mount device df -h ] 
    umount /dev/sdb1
