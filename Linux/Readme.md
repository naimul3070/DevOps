## For Allow AWS instance SSH

##### First open the file
    vim /etc/ssh/sshd_config
##### add the line
    PubkeyAcceptedAlgorithms +ssh-rsa
##### After sade restart the system
    systemctl restart sshd

### Now you can conect the instance with any ssh tools

# HAPPY LINUX