# Configuration
Open `/boot/config.txt`.
```bash
sudo nano /boot/config.txt
```
Add the lines you want.
```bash
# Optimizations for headless server
# free up memory for the CPU by reducing GPU
gpu_mem=32
# disable Bluetooth
dtoverlay=disable-bt
# disable WiFi
dtoverlay=disable-wifi
```
Reboot.
```bash
sudo reboot
```
