This is a small tutorial on how to run HORNET as a systemd service. This tutorial was tested on an Ubuntu 18.04 x86_64 VPS but you can transfer it to other linux systems as well.

### Preparations
- Setup your system and update it with `sudo apt update && sudo apt upgrade -y`
- Install and enable a firewall of your choice (e.g. ufw | optional but recommended)
- Create a HORNET user with `sudo useradd -s /bin/bash -m hornet`
- Install some tools: `sudo apt install curl wget jq -y`

### Setup HORNET
1. `cd /home/hornet`
2. Download the [latest HORNET release](https://github.com/gohornet/hornet/releases/latest) for your system (e.g. for HORNET 0.2.5 x86_64):
```bash
sudo -u hornet wget -O /tmp/hornet.tar.gz https://github.com/gohornet/hornet/releases/download/v0.2.5/HORNET-0.2.5_Linux_x86_64.tar.gz && sudo -u hornet mkdir -p /tmp/hornet && sudo -u hornet tar xzf /tmp/hornet.tar.gz -C /tmp/hornet && rm /tmp/hornet.tar.gz && sudo -u hornet mv /tmp/hornet/hornet /home/hornet/hornet &&  sudo -u hornet mv -vn /tmp/hornet/config.json /home/hornet/config.json && sudo -u hornet rm -r /tmp/hornet
```
3. Setup the service
```bash
cat << 'EOF' | sudo tee /lib/systemd/system/hornet.service > /dev/null
[Unit]
Description=HORNET Fullnode
After=network.target

[Service]
WorkingDirectory=/home/hornet
User=hornet
TasksMax=infinity
KillSignal=SIGTERM
TimeoutStopSec=infinity
ExecStart=/home/hornet/hornet -c config
SyslogIdentifier=HORNET
Restart=on-failure
RestartSec=1200

[Install]
WantedBy=multi-user.target
Alias=hornet.service

EOF
```
4. Enable the service 
```bash
sudo systemctl daemon-reload && sudo systemctl enable hornet.service
```
5. Add neighbors to your config (edit the example neighbors in config.json)
```bash
nano config.json
```
6. Download the latest snapshot 
```bash
wget https://dbfiles.iota.org/mainnet/hornet/latest-export.gz.bin
```
7. Start the HORNET service
```bash
sudo service hornet start
```
8. Done, watch the logs
```bash
sudo journalctl -u hornet -f
```
Exit the logs with `CTRL+c`