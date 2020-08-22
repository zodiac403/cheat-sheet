# Raspberry Pi Basic Setup

This checklist sets up a Raspberry Pi with the following features:

- Current Raspian OS installed
- Accessible via Wi-Fi and SSH
- Rudimentary security hardening

## Setup Device and Install Operating System

The general entry point for Raspberry Pi setup, see the [Setup documentation>](https://www.raspberrypi.org/documentation/setup/).

> TODO: Download link

Create SD card with OS image.

```bash
unzip -p 2019-09-26-raspbian-buster.zip | sudo dd of=/dev/sdX bs=4M conv=fsync status=progress
```

## Headless Wi-Fi Configuration

Network connectivity can be prepared before booting the device with [wireless headless configuration](https://www.raspberrypi.org/documentation/configuration/wireless/headless.md).

### Enable SSH

To enable SSH, place an empty file in the [boot partition](https://www.raspberrypi.org/documentation/configuration/boot_folder.md).

```bash
cd /PATH/TO/boot/
sudo touch ssh
```

### Configure Wi-Fi

Do not store the Wi-Fi password in text. For WPA connections, use `wpa_passphrase`. Omit passphrase in the first call to keep it out of bash history.

```bash
wpa_passphrase <ssid> [passphrase]
```

To configure the Wi-Fi client, create and edit a file in the [boot partition](https://www.raspberrypi.org/documentation/configuration/boot_folder.md).

```bash
cd /PATH/TO/boot/
sudo nano wpa_supplicant.conf
```

Make sure that this creates a new file. Place the content. `country` is a two letter country code (e.g. `GB` or `DE`) and `network` is the output of `wpa_passphrase`.

```ini
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<Insert country code here>

network={
   ssid="<Name of your Wi-Fi>"
   psk="<Password for your Wi-Fi>"
}
```

## Boot Up

After booting, ssh into the device with default credentials user `pi` and password `raspberry`.

```bash
ssh pi@rasperrypi
```

Update installed software.

```bash
sudo apt-get update && sudo apt-get upgrade
```

## Basic Security Configuration

[Recommendation](https://www.raspberrypi.org/documentation/configuration/security.md).

### Change Default User

Create new user.

```bash
sudo adduser <user>
sudo usermod -a -G adm,dialout,cdrom,sudo,audio,video,plugdev,games,users,input,netdev,gpio,i2c,spi <user>
```

Delete default user.

```bash
sudo deluser -remove-home pi
```

### Register SSH Key

> TODO

### Configure Fire Wall

> TODO
