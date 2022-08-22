## Linux firewall command


### ufw – Used by Ubuntu and Debian based system to manage the firewall.
### firewalld – Used by RHEL, CentOS and clones. It is a dynamic solution to manage the firewall.

## Ubuntu Start

#### ufw is easy to use app for managing a Linux firewall and aims to provide an easy to use interface for the user. It is the default on Ubuntu and can be installed on Debian, CentOS, and other Linux distros. 
		sudo apt install ufw

### Check the ufw status
		sudo firewall-cmd --state
		
### Stop the ufw on Linux
		sudo ufw disable
		
### sudo systemctl disable ufw
		sudo systemctl disable ufw
		
### Verify that the ufw is gone
		sudo ufw status
		sudo systemctl status ufw
		
### How to enable the ufw ?
		sudo systemctl enable ufw
		sudo ufw enable
		
### Verify that the ufw is gone
		sudo ufw status
		sudo systemctl status ufw
## Ubuntu End

## RHEL, CentOS Start 

### Is firewalld running on my system?
		sudo firewall-cmd --state

### Stop the the firewalld
		sudo systemctl stop firewalld

### Disable the FirewallD service at boot time
		sudo systemctl disable firewalld
		sudo systemctl mask --now firewalld
### Verify that the FirewallD is gone
		systemctl status firewalld
		
### How to enable the firewalld again?

		sudo systemctl unmask --now firewalld
		sudo systemctl enable firewalld
		sudo systemctl start firewalld
		
## verify that the firewalld started ##
		sudo firewall-cmd --state

## RHEL, CentOS End
