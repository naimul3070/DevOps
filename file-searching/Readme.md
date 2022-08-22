

# File searching date,time,month sequence for delete modify etc

# For executable command, use command end of -exec 

## Command execute from any directory [here directory path has been mentioned] 

### searching date and time wise

    find /var/opt/mssql/data/mssqllinux/* -type f ! -name "*.trn" -newermt '26 Jun 2022 23:00:00' -exec ls -la {} \;
    
    find /var/opt/mssql/data/mssqllinux/* -type f ! -name "*.trn" -newermt '26 Jun 2022' -exec ls -la {} \;

    find /var/opt/mssql/data/mssqllinux/* -type f ! -newermt '26 Jun 2022 23:00:00' -exec ls -la {} \;
    
## Command execute from current directory

    find . -type f ! -newermt '27 Jun 2022 22:00:00' -exec ls {} \;
    
## Command execute from any directory [here directory path has been mentioned] 

### searching day wise [ -mtime +0  0 means today 1 means yeasterday ...... n , -1 means current date ]

    find /var/opt/mssql/data/mssqllinux/* -name "*.bak" -type f -mtime +0 -print
    
    find /var/opt/mssql/data/mssqllinux/* -name "*.bak" -type f -mtime -1 -exec ls -la {} \;
    
### searching minutes wise [ -amin +760 ]

    find /var/opt/mssql/data/mssqllinux/* -name "*.log" -type f -amin +760 -print
