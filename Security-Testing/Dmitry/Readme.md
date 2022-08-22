#	Dmitry complete Guide		

<p>DMitry is a UNIX/(GNU)Linux command line application written in C,Deepmagic Information Gathering Tool. DMitry can find possible subdomains, email addresses, uptime information, perform tcp port scan, whois lookups, and more.[ command always case sensitive ] </p>

### How to run dmity? After run we can see the possile execuatable command instruction.	
		dmitry
	
### we can use default command for gathering all of information at once.	
		dmitry domain.com 
	
### Save output to %host.txt or to file specified by -o file	
		dmitry domain.com -o result.txt
	
### Perform a whois lookup on the IP address of a host.	
		dmitry domain.com -i
	
### Perform a whois lookup on the domain name of a host	
		dmitry domain.com -w
	
### Perform a search for possible subdomains	
		dmitry domain.com -s
	
### Perform a search for possible email addresses	
		dmitry domain.com -e
	
### Perform a TCP port scan on a host	
		dmitry domain.com -p
	
### we can use our requirments options value for gathering output	
		dmitry domain.com -p -i -s -o result