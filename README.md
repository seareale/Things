# Penta-SATA-HAT-for-Rock-pi-4

Ubuntu Server 18.04(https://wiki.radxa.com/Rockpi4/downloads)


## Get public key
```bash
wget -O -  apt.radxa.com/stretch/public.key | sudo apt-key add - 
```
Edit your `/etc/apt/sources.list` and add the following:
```bash
deb http://apt.radxa.com/stretch/ stretch main
```

## Rock Pi 4 setting
```bash
sudo apt-get update && sudo apt-get upgrade
curl -sL https://rock.sh/get-rockpi-penta | sudo -E bash -
sudo reboot
```

## OMV5
```bash
sudo curl -sSL https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
sudo reboot
```
