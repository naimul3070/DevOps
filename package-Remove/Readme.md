# Remove package , file, folder

### Show package list	
    dpkg --list

### package search	
    dpkg -l | grep -i docker
	
### Remove Package	
    sudo apt remove --purge docker-ce docker-ce-cli containerd.io
    
### Remove Package with prefix 
    sudo apt remove --purge nginx*
	
### Remove file/folder 	
    sudo rm -rf /var/lib/docker
	
### Remove File/folder	
    sudo rm -rf /etc/postgresql-common
	
### Auto remove unused file	
    sudo apt autoremove -y
	
### Auto Clean	
    sudo apt autoclean
	
### Clean	
    sudo apt clean
	
### Remove & clean	
    sudo apt purge --auto-remove apache2
	
### Remove & clean	
    sudo apt --purge remove openproject*
	
