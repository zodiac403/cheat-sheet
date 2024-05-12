# Debian-like Systems - Unattended Upgrade

Package home page: https://wiki.debian.org/UnattendedUpgrades

How to install

```sh
sudo apt-get install unattended-upgrades apt-listchanges
```

How to evaluate log files

```sh
pushd WKDIR
cp /var/log/unattended-upgrades/unattended-upgrades.* ./
gzip -d FILE.gz
cat FILE
popd
```
