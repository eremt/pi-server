# Server configuration

## Headless server optimization
Run this command.
```bash
curl -s https://raw.githubusercontent.com/eremt/pi-server/master/configs/headless-optimizations | sudo tee -a /boot/config.txt
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

## PoE Hat fan speed
If using the PoE Hat the fans can get a little noisy. To change this run this command:
```bash
curl -s https://raw.githubusercontent.com/eremt/pi-server/master/configs/poe-fan-speed | sudo tee -a /boot/config.txt
```
This will append these lines to `/boot/config.txt`:
```bash
# PoE Hat fan speed
dtparam=poe_fan_temp0=50000
dtparam=poe_fan_temp1=60000
dtparam=poe_fan_temp2=70000
dtparam=poe_fan_temp3=80000
```
Each entry represents a fan speed and what temperature triggers it. `50000` means 50°C and so on.

Reboot.
```bash
sudo reboot
```
