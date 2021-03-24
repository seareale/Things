# Penta-SATA-HAT-for-Rock-pi-4

Debian 9 Desktop(https://wiki.radxa.com/Rockpi4/downloads)


## Get public key
```bash
export DISTRO=stretch-stable
echo "deb http://apt.radxa.com/$DISTRO/ ${DISTRO%-*} main" | sudo tee -a /etc/apt/sources.list.d/apt-radxa-com.list
wget -O - apt.radxa.com/$DISTRO/public.key | sudo apt-key add -
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install rockchip-overlay
sudo apt-get install -y rockpi4b-rk-u-boot-latest
```

## Rock Pi 4 setting
```bash
curl -sL https://rock.sh/get-rockpi-penta | sudo -E bash -
sudo reboot

sudo rm /var/lib/dpkg/status
sudo vi /var/lib/dpkg/status 
  :wq
```

## OMV4
```bash
cat <<EOF >> /etc/apt/sources.list.d/openmediavault.list
deb http://packages.openmediavault.org/public arrakis main
# deb http://downloads.sourceforge.net/project/openmediavault/packages arrakis main
## Uncomment the following line to add software from the proposed repository.
# deb http://packages.openmediavault.org/public arrakis-proposed main
# deb http://downloads.sourceforge.net/project/openmediavault/packages arrakis-proposed main
## This software is not part of OpenMediaVault, but is offered by third-party
## developers as a service to OpenMediaVault users.
# deb http://packages.openmediavault.org/public arrakis partner
# deb http://downloads.sourceforge.net/project/openmediavault/packages arrakis partner
EOF
```
```bash
export LANG=C.UTF-8
export DEBIAN_FRONTEND=noninteractive
export APT_LISTCHANGES_FRONTEND=none
wget -O "/etc/apt/trusted.gpg.d/openmediavault-archive-keyring.asc" https://packages.openmediavault.org/public/archive.key
apt-key add "/etc/apt/trusted.gpg.d/openmediavault-archive-keyring.asc"
apt-get update
apt-get --yes --auto-remove --show-upgraded \
	--allow-downgrades --allow-change-held-packages \
	--no-install-recommends \
	--option Dpkg::Options::="--force-confdef" \
	--option DPkg::Options::="--force-confold" \
	install postfix openmediavault-keyring openmediavault

# Initialize the system and database.
omv-initsystem

# Rebuild configurations.
omv-mkconf interfaces
omv-mkconf issue

# Display the login information.
cat /etc/issue
```

---

### fan
```bash
sudo vi /etc/rockpi-penta.conf
sudo systemctl restart rockpi-penta.service
```
