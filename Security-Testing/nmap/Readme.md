#	Nmap complete Guide		

<p>Nmap is a network scanner (Network Mapper)created by Gordon Lyon. Nmap is used to discover hosts and services on a computer network by sending packets and analyzing the responses.Nmap allows you to scan your network and discover not only everything connected to it, but also a wide variety of information about what's connected, what services each host is operating, and so on.It allows a large number of scanning techniques, such as UDP, TCP connect (), TCP SYN (half-open), and FTP.		
		
		
		 </p>
		 
### Run nmap >>after run nampe we can follow the possible options to execute the command 	
		
		nmap
	
### we can use this comman for scanning a single IP	
	
		nmap <ip address>
	
### we can use this comman for scanning a Host IP	

		nmap <host name>
	
### we can use this comman for scanning a  IP range	

		nmap <ip address range>
	
### we can use this comman for scanning a single port 	

		nmap -p <port number> <IP address>
	
### we can use this comman for scanning a rang of port 	

		nmap -p <range of port number> <IP address>
	
### Scanning 100 most common ports.	

		nmap -f <IP address>
	
### Scan using TCP SYN scan.	
		
		nmap -sS <IP address>
	
### Scan using TCP SYN scan.(for 3 way handshak)	

		nmap -sU 20.195.48.125
	
### Scan for UDP SYN .	
		
		nmap -sU <IP address>
	
### we can check if firewall is enable	 

		nmap -sA <IP address>
	
### set a output file	

		nmap -f <IP> -oA or -oX  file_name
	
### we can follow the nmap help option	

		nmap --help
	
### Command	sample

		nmap -T4 -sV -A ip -oN nmap_meta
		
### We can use linux tools or windows tools
