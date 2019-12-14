# Docker
## Install
Install Docker.
```bash
curl -sSL https://get.docker.com | sh
```
Add user to the "docker" group.
```bash
sudo usermod -aG docker <USERNAME>
```
Logout and log back in for the changes to take effect.

Test Docker installation.
```bash
docker run hello-world
```
## Install Docker-compose
Install dependencies and remove `python-configparser`.
```bash
sudo apt install libffi-dev libssl-dev python python-pip
```
```bash
sudo apt remove python-configparser
```
Then install docker-compose with PIP.
```
sudo pip install docker-compose
```
