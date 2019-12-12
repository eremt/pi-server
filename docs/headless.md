# Headless setup
## SSH
To enable SSH create a file called `ssh` in the /boot directory.
```bash
touch ssh
```
## WiFi
For optional WiFi setup, create a file called `wpa_supplicant.conf` in the /boot directory.
```bash
nano wpa_supplicant.conf
```
Paste the following contents and replace country, ssid and psk values.
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<ISO 3166 Country Code>

network={
 ssid="<WiFi SSID>"
 psk="<WiFi Password>"
}
```
Now you can start the Raspberry PI and go to the next step: [Replace default user](https://github.com/eremt/pi-server/blob/master/docs/user.md).
