# Install SSl on ubuntu

## Install Certbot in Ubuntu with PIP

> First, install PIP:
``` 
sudo apt install python3 python3-venv libaugeas0
```
> Set up a virtual environment:
```
sudo python3 -m venv /opt/certbot/

sudo /opt/certbot/bin/pip install --upgrade pip
```
> Install Certbot on Apache:
```
sudo /opt/certbot/bin/pip install certbot certbot-apache
```
> Install Certbot on NGINX:
```
sudo /opt/certbot/bin/pip install certbot certbot-nginx
```

> Create a symlink to ensure Certbot runs:
```
sudo ln -s /opt/certbot/bin/certbot /usr/bin/certbot
```
## Install Certbot in Ubuntu with snapd

> Install snapd:
```
sudo apt install snapd
```
> Ensure you have the latest snapd version installed:
```
sudo snap install core; sudo snap refresh core
```

> Install Certbot with snapd:
```
sudo snap install --classic certbot
```
> Create a symlink to ensure Certbot runs:
```
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

## Create an SSL Certificate with Certbot

### Choose the best option for your needs.

> Create SSL certs for all domains and configure redirects in the web server:
```
sudo certbot --apache

sudo certbot --nginx
```

> Create SSL certs for a specified domain (recommended if you’re using your system hostname):
```
sudo certbot --apache -d [domain] -d www.[domain]

sudo certbot --nginx -d [domain] -d www.[domain]
```

### If prompted, choose whether to redirect HTTP traffic to HTTPS – 1 (no redirect, no further changes to the server) or 2 (redirect all HTTP requests to HTTPS).
