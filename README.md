# Penta-SATA-HAT-for-Rock-pi-4

Ubuntu Server 18.04(https://wiki.radxa.com/Rockpi4/downloads)


## Rock Pi 4 setting
```bash
wget -O - apt.radxa.com/bionic/public.key | sudo apt-key add -
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install curl
curl -sL https://rock.sh/get-rockpi-penta | sudo -E bash -
```

## OMV5
```bash
wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```
