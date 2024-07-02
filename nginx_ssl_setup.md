# Nginx and SSL Setup Documentation

## Table of Contents
1. [Introduction](#introduction)
2. [Nginx Setup](#nginx-setup)
    - [Installation](#installation)
    - [Configuration](#configuration)
3. [SSL Setup with Certbot](#ssl-setup-with-certbot)
    - [Installing Certbot](#installing-certbot)
    - [Generating SSL Certificates](#generating-ssl-certificates)
    - [Auto-Renewal Setup](#auto-renewal-setup)
4. [Conclusion](#conclusion)

---

## Introduction

This document provides step-by-step instructions for setting up Nginx web server and SSL certificates using Certbot for the domains `buysell.saifsolution.com`, `fixit.saifsolution.com`, `it.saifsolution.com`, `saifsolution.com`, and `spevent.saifsolution.com`.

---

## Nginx Setup
    

### Installation

1. **Update Package Repository:**
   ```bash
   sudo apt update

## Install Nginx:

    sudo apt install nginx

## Configuration
### Configure Nginx Sites:

### Create configuration files for each domain under /etc/nginx/sites-available/.

### Example configuration for buysell.saifsolution.com:

    server {
    listen 80;
    server_name buysell.saifsolution.com;
    root /var/www/buysell.saifsolution.com;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ /index.php?$args;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php-fpm.sock;
    }

    location ~ /\.ht {
        deny all;
    }
}

## Enable Sites:

    sudo ln -s /etc/nginx/sites-available/buysell.saifsolution.com /etc/nginx/sites-enabled/

## Test and Reload Nginx:

    sudo nginx -t
    sudo systemctl reload nginx


# SSL Setup with Certbot
### Installing Certbot
### Install Certbot:

    sudo apt install certbot python3-certbot-nginx


# Generating SSL Certificates
### Generate SSL Certificates:

### Run Certbot for each domain to obtain SSL certificates:

    sudo certbot --nginx -d buysell.saifsolution.com -d fixit.saifsolution.com -d it.saifsolution.com -d saifsolution.com -d spevent.saifsolution.com

#### Follow the prompts to configure SSL.

# Auto-Renewal Setup

### Verify Certbot Timer:

### Check the status of the Certbot timer for automatic renewal:

    sudo systemctl status certbot.timer

### Ensure the timer is active and scheduled correctly.

### Manual Renewal Test:

### Optionally, test manual certificate renewal before expiry:

    sudo certbot renew --dry-run

### Reload Nginx:
### After obtaining SSL certificates, reload Nginx to apply changes:

    sudo systemctl reload nginx


# Conclusion
#### This documentation covers the setup of Nginx web server and SSL certificates using Certbot for the domains buysell.saifsolution.com, fixit.saifsolution.com, it.saifsolution.com, #### saifsolution.com, and spevent.saifsolution.com. Ensure to monitor certificate expiration and renewals periodically.

#### For further assistance or troubleshooting, refer to Certbot documentation or consult with your system administrator.



### Usage:
1. Copy the above Markdown content into a file named `nginx_ssl_setup.md`.
2. Save the file.
3. You can open and view this file with any Markdown viewer or editor.

This document provides a structured guide on setting up Nginx and SSL with Certbot, tailored specifically for your domains. Adjust any specific details or paths as per your server configuration if needed.
