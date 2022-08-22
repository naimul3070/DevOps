# Welcome to mssql backup process 

# create backup to external device using by differnet machine 

# copy backup file to external device [usb]

### Go to usb directory 

	cd /media/ibos/My_Passport/DB-FULL-BACKUP
	
	ls
	
### Connect ssh to database machin

	sshpass -p "ibos@123" sftp ibos@10.209.99.244

	ls
	
### Change the directory to mssql data backup location 

	cd /var/opt/mssql/data/

	ls

### Copy the whole backup file

	get -r mssqllinux
	
### Or copy the single database backup file

	cd /var/opt/mssql/data/mssqllinux/
	
	ls
	
	get -r SME
