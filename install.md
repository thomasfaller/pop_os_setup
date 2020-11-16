# Pop!\_OS Setup

note: those steps are taken from https://mutschler.eu/linux/install-guides/pop-os-btrfs/

## After install

```bash
sudo sed -i 's/us./uk./' /etc/apt/sources.list
sudo local-gen en_IE.UTF.8
sudo local-gen en_GB.UTF.8
sudo update-locale LANG=en_IE.UTF-8
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
sudo apt autoremove
sudo fwupdmgr get-devices
sudo fwupdmgr get-updates
sudo fwupdmgr update
sudo reboot now
```

## Software to install

### Docker

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce docker-compose docker-ce-cli containerd.io
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

### Node Version Manager

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.0/install.sh | bash
# logout and back in
nvm install node
nvm install --lts
nvm use --lts
```
