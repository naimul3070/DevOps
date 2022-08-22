#	SkipFish complete Guide		

<p>Skipfish is a free and open-source Automated Penetration Testing (APT) tool for security researchers that can be found on GitHub. Skipfish is used for information gathering and testing the security of websites and web servers. Skipfish is one of the most user-friendly and effective penetration testing tools available. It comes with several integrated tools for penetrating testing the target system. This tool is also called an active web application security reconnaissance tool. This tool works and maps the target site's console using recursive crawls and dictionary-based probes. This tool displays all of the active security checks in the domain. Finally, this tool creates a report that can be utilized for security assessments.[ command always case sensitive ] </p>

### Git clone skipfish	 
		git clone https://gitlab.com/kalilinux/packages/skipfish.git 
	
### See the list skipfish is available !	
		ls 
	
### change directory to skipfish	
		cd skipfish
	
### We can use the Skipfish tool to scan a WordPress website with the help of its IP address.	
		skipfish -o 202 http://192.168.1.202
	
### we can see help option to execute other script	
		skipfish -h