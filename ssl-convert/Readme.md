# SSL Convert

### Convert PEM to CRT

    openssl x509 -outform der -in your-cert.pem -out your-cert.crt
    
### Convert PEM to private KEY

    openssl rsa -outform der -in private.pem -out private.key
    
    
### Convert SSL online 

<a href="https://rvssl.com/ssl-converter/">Convert Certificate PEM to PFX</a> 

>> Upload cert.pem > select standred PEM

>> upload private_key.pem 

>> set PEX password 

