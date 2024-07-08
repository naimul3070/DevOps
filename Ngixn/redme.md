# Step-by-Step Guide to Deploying Multiple Applications on an Ubuntu Server
## Diagram
Here's a simple diagram illustrating the deployment architecture:

![image](https://github.com/naimul3070/DevOps/assets/50922314/04df8c12-6c8a-4770-9c9e-a0893608e269)

  # Deployment Guide

## Steps

### 1. Initial Setup
- **Update the system:**
  ```sh
  sudo apt update
  sudo apt upgrade -y

#### Install necessary packages:
    sudo apt install -y nginx git nodejs npm
#### 2. Clone the Repositories
#### Navigate to the project directory:
    cd /var/www
#### Clone the Next.js application repositories:
    git clone [your_nextjs_repo] devapi.aayattours.com
    git clone [your_nextjs_repo] devapi.muslimcouplesretreat.com
### 3. Install Dependencies and Build the Applications
#### Install dependencies:
    cd /var/www/devapi.aayattours.com
    npm install
    npm run build
  
#### Repeat for the second application:

    cd /var/www/devapi.muslimcouplesretreat.com
    npm install
    npm run build
  
### 4. Configure PM2 for Process Management
#### Install PM2 globally:

    sudo npm install pm2@latest -g
  
#### Start the applications with PM2:
    cd /var/www/devapi.aayattours.com
    pm2 start npm --name "devapi.aayattours.com" -- start

    cd /var/www/devapi.muslimcouplesretreat.com
    pm2 start npm --name "devapi.muslimcouplesretreat.com" -- start
    
#### Save the PM2 process list and setup startup script:

    pm2 save
    pm2 startup
####b 5. Nginx Configuration
### Create Nginx configuration files:

    sudo nano /etc/nginx/sites-available/dev.aayattours.com
    sudo nano /etc/nginx/sites-available/devapi.aayattours.com
    sudo nano /etc/nginx/sites-available/devapi.muslimcouplesretreat.com
#### Add the following configurations respectively:
### 1.
    # /etc/nginx/sites-available/dev.aayattours.com
    server {
        listen 80;
        server_name dev.aayattours.com;
    
        location / {
            proxy_pass http://localhost:8080;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }
      }
    
#### 2.

    # /etc/nginx/sites-available/devapi.aayattours.com
    server {
        listen 80;
        server_name devapi.aayattours.com;
    
        location / {
            proxy_pass http://localhost:8081;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }
      }

#### 3.

    # /etc/nginx/sites-available/devapi.muslimcouplesretreat.com
    server {
        listen 80;
        server_name devapi.muslimcouplesretreat.com;
    
        location / {
            proxy_pass http://localhost:8082;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }
      }
    
#### Enable the configurations:

    sudo ln -s /etc/nginx/sites-available/dev.aayattours.com /etc/nginx/sites-enabled/
    sudo ln -s /etc/nginx/sites-available/devapi.aayattours.com /etc/nginx/sites-enabled/
    sudo ln -s /etc/nginx/sites-available/devapi.muslimcouplesretreat.com /etc/nginx/sites-enabled/
  
#### Test and reload Nginx:

      sudo nginx -t
      sudo systemctl reload nginx
#### 6. Firewall Configuration
### Allow necessary ports:

      sudo ufw allow 80
      sudo ufw allow 8080
      sudo ufw allow 8081
      sudo ufw allow 8082
      sudo ufw allow 443
      sudo ufw enable
      
#### 7. Setup SSL with Certbot
### Install Certbot:

    sudo apt install certbot python3-certbot-nginx
  
#### Obtain and install SSL certificates:

    sudo certbot --nginx -d dev.aayattours.com
    sudo certbot --nginx -d devapi.aayattours.com
    sudo certbot --nginx -d devapi.muslimcouplesretreat.com
  
#### Verify Certbot renewal:

    sudo certbot renew --dry-run
    
### Conclusion
#### You have successfully deployed three applications on an Ubuntu server, configured them to run with PM2, and set up Nginx as a reverse proxy with SSL certificates from Certbot. These steps ensure that your applications will run continuously, even after server reboots, and are secured with HTTPS.



