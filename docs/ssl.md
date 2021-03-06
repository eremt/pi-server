# Let's encrypt
Before using certbot configure at least one site or certbot will overwrite the default configuration file. There's an example configuration in the [NGINX section](https://github.com/eremt/pi-server/blob/master/docs/nginx.md#configure-a-site).

Install certbot and dependencies.
```bash
sudo apt install certbot python-certbot-nginx
```
Run certbot to create certificate.
```bash
sudo certbot --nginx
```
If you haven't already make sure https traffic is allowed.
```bash
sudo ufw allow https
```
Certbot adds a job to attempt renewal twice a day. If any certificate has less than 30 days to expiry it will be renewed.
