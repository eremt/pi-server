# Configuration
Run this command.
```bash
curl -s https://raw.githubusercontent.com/eremt/pi-server/master/configs/config.txt | sudo tee -a /boot/config.txt
```
The command appends these lines to `/boot/config.txt`.
```bash
# Optimizations for headless server
# free up memory for the CPU by reducing GPU
gpu_mem=32
# disable Bluetooth
dtoverlay=disable-bt
# disable WiFi
#dtoverlay=disable-wifi
```
Note that disabling WiFi is commented out, if you're on Ethernet open `/boot/config.txt`.
```bash
sudo nano /boot/config.txt
```
And uncomment the  last line.
```bash
# disable WiFi
dtoverlay=disable-wifi
```
Reboot.
```bash
sudo reboot
```
