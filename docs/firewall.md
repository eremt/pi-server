# Firewall
## Install UFW
```bash
sudo apt install ufw
```
Before enabling make sure to allow ssh so you don't get disconnected.
```bash
sudo ufw allow ssh
```
Then enable the firewall and ensure it starts on boot.
```bash
sudo ufw enable
```

## Open ports
To allow traffic on ports 80 or 443.
```bash
sudo ufw allow http
```
```bash
sudo ufw allow https
```
