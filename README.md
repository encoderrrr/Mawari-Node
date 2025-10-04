![ ](https://raw.githubusercontent.com/encoderrrr/encoderrrr/refs/heads/main/2.JPG?token=GHSAT0AAAAAACR7R24HO37G7CEGBK47DJTK2HA6WZA)
# Install Dependecies
```shell
sudo apt-get update && sudo apt-get upgrade -y
```
```shell
sudo apt install curl ufw iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
# Install Docker
```shell
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test Docker
sudo docker run hello-world
```
# Create Folder
```shell
mkdir -p ~/mawari
cd ~/mawari
```
# set your node image name
```shell
export MNTESTNET_IMAGE=us-east4-docker.pkg.dev/mawarinetwork-dev/mwr-net-d-car-uses4-public-docker-registry-e62e/mawari-node:latest
```
***set your owner wallet address from which Guardian NFTs will be delegated***
> set your address
```shell
export OWNER_ADDRESS=0x123abc
```
# Create Screen
```shell
screen -S mawari
```
# Running Guardian Node
```shell
docker run --pull always -v ~/mawari:/app/cache  -e OWNERS_ALLOWLIST=$OWNER_ADDRESS $MNTESTNET_IMAGE
```
- [ ] Check Logs & Find Your Burner Address
![تصویر](https://raw.githubusercontent.com/encoderrrr/Mawari-Node/main/1.JPG)

- [ ] get testnet token for main wallet after this Send 1 token from your main wallet to your ***burner** wallet

# go to dashboard
https://app.testnet.mawari.net/

- Select your IDs
- Delegate
- Enter your burner address
- Confirm

![ ](https://raw.githubusercontent.com/encoderrrr/Mawari-Node/refs/heads/main/1.JPG) 
