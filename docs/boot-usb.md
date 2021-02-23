# Boot from USB
Start by updating the system:
```bash
sudo apt update
sudo apt upgrade
sudo rpi-update
```
Reboot.

## Pi 4
Update the EEPROM by running:
```bash
sudo rpi-eeprom-update -d -a
```
Reboot.

When the PI boots run `raspi-config`:
```bash
sudo raspi-config
```
Make sure the Boot ROM Version is the latest and change the USB boot order.

## Pi 3
Enable USB boot mode by adding this line to `/boot/config.txt`:
```bash
echo program_usb_boot_mode=1 | sudo tee -a /boot/config.txt
```
Reboot.

Make sure the OTP was programmed with:
```bash
vcgencmd otp_dump | grep 17:
```
The output should be `17:3020000a`.

Start securing the PI in the next step: [User setup](https://github.com/eremt/pi-server/blob/master/docs/user.md).
