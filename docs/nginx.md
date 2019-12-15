# NGINX
## Install NGINX
First install the `nginx` package.
```bash
sudo apt install nginx
```
Start the server.
```bash
sudo service nginx start
```
## Configure a site
Create a configuration file for a domain.
```bash
sudo nano /etc/nginx/sites-available/<DOMAIN NAME>
```
Paste the content below.
```bash
server {
  listen 80;
  listen [::]:80;

  server_name <DOMAIN NAME>;
  gzip on;
  gzip_types text/plain text/css application/javascript;

  root /srv/www/<DOMAIN NAME>;
  index index.html;

  location / {
    try_files $uri $uri/ =404;
  }
}
```
Symlink the configuration to `/etc/nginx/sites-enabled` to enable it.
```bash
sudo ln -s /etc/nginx/sites-available/<DOMAIN NAME> /etc/nginx/sites-enabled/<DOMAIN NAME>
```
Restart `nginx`.
```bash
sudo service nginx restart
```
