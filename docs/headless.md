# Headless setup
## SSH
To enable SSH all you have to do is create an empty file called `ssh` in the /boot directory.

## WiFi
If you want WiFi create a file called `wpa_supplicant.conf` in the /boot directory with the following contents, replace country, ssid and psk:
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<ISO 3166 Country Code>

network={
 ssid="<WiFi SSID>"
 psk="<WiFi Password>"
}
```

Next you can setup your PI to [boot from USB](https://github.com/eremt/pi-server/blob/master/docs/boot-usb.md) or start securing it by [removing the default user](https://github.com/eremt/pi-server/blob/master/docs/user.md).
