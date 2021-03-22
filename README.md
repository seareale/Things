# Penta-SATA-HAT-for-Rock-pi-4

Debian 9 Desktop(https://wiki.radxa.com/Rockpi4/downloads)


## Get public key
```bash
wget -O -  apt.radxa.com/stretch/public.key | sudo apt-key add - 
```

## Rock Pi 4 setting
```bash
sudo apt-get update && sudo apt-get upgrade
curl -sL https://rock.sh/get-rockpi-penta | sudo -E bash -
sudo reboot
```
### fan
```bash
sudo vi /etc/rockpi-penta.conf
sudo systemctl restart rockpi-penta.service
```

## OMV4
```bash

sudo curl -sSL https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
sudo reboot
```
