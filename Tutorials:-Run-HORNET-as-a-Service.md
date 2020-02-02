This is a small tutorial on how to run HORNET as a systemd service. This tutorial was tested on an Ubuntu 18.04 x86_64 VPS but you can transfer it to other linux systems as well.

### Preparations

- Setup your system and update it with `sudo apt update && sudo apt upgrade -y`
- Install and enable a firewall of your choice (e.g. ufw | optional but recommended)
- Create a HORNET user with `sudo useradd -s /bin/bash -m hornet`
- Install some tools: `sudo apt install curl wget jq -y`

### Setup HORNET

1. `cd /home/hornet`
2. Download the [latest HORNET release](https://github.com/gohornet/hornet/releases/latest) for your system (e.g. for HORNET 0.3.0 x86_64):

```bash
sudo -u hornet wget -O /tmp/hornet.tar.gz https://github.com/gohornet/hornet/releases/download/v0.3.0/HORNET-0.3.0_Linux_x86_64.tar.gz && sudo -u hornet tar xzf /tmp/hornet.tar.gz && rm /tmp/hornet.tar.gz && sudo -u hornet mv /tmp/HORNET-0.3.0_Linux_x86_64/hornet /home/hornet/hornet &&  sudo -u hornet mv -vn /tmp/HORNET-0.3.0_Linux_x86_64/config.json /home/hornet/config.json &&  sudo -u hornet mv -vn /tmp/HORNET-0.3.0_Linux_x86_64/neighbors.json /home/hornet/neighbors.json && sudo -u hornet rm -r /tmp/HORNET-0.3.0_Linux_x86_64
```

3. Setup the service

```bash
cat << 'EOF' | sudo tee /lib/systemd/system/hornet.service > /dev/null
[Unit]
Description=HORNET Fullnode
Wants=network-online.target
After=network-online.target

[Service]
WorkingDirectory=/home/hornet
User=hornet
SyslogIdentifier=HORNET
LimitNOFILE=4096
StandardOutput=syslog
StandardError=syslog
PrivateDevices=yes
PrivateTmp=yes
ProtectSystem=full
ProtectHome=yes
KillSignal=SIGTERM
TimeoutSec=1200
Restart=always
ExecStart=/home/hornet/hornet -c config

[Install]
WantedBy=multi-user.target

EOF
```

4. Enable the service

```bash
sudo systemctl daemon-reload && sudo systemctl enable hornet.service
```

5. Add neighbors to your neighbors config (edit the example neighbors in neighbors.json)

```bash
nano neighbors.json
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
