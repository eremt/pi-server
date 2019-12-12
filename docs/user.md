# User setup
On first boot login on the default user `pi`.
```bash
ssh pi@<IP-ADDRESS>
```
You will be promted to enter the password, the default is `raspberry`.

Once logged in start by updating Raspbian.
```bash
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
```
## Create new user
Create a new user.
```bash
sudo adduser <USERNAME>
```
Add sudo and rest of the persmissions.
```bash
sudo usermod -aG adm,dialout,cdrom,sudo,audio,video,plugdev,games,users,input,netdev,gpio,i2c,spi <USERNAME>
```
## Remove default user `pi`
To remove the default user first kill its process.
```bash
sudo pkill -u pi
```
Then remove the user and its home directory. This might break some functionality.
```bash
sudo deluser -remove-home pi
```
## SSH login
Run `ssh-copy-id` on the computer that hosts your public key to copy it to the Raspberry pi.
```bash
ssh-copy-id <USERNAME>@<IP-ADDRESS>
```
Then disable password login.
```bash
sudo nano /etc/ssh/sshd_config
```
Make sure the following lines are present.
```bash
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```
Save the file and restart the ssh system.
```bash
sudo service ssh reload
```

Now that you have a user you can go to the next step: [Firewall](https://github.com/eremt/pi-server/blob/master/docs/firewall.md).
