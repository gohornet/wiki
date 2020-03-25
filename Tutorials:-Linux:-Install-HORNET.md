This is a small tutorial on how to install HORNET using our apt repository.

### Preparations

- Setup an e.g. Ubuntu (>= 16.04) server with at least 1GB RAM
- Optional but recommended: Add a ssh key, activate a firewall,...
- Update your system with:<br>
  ```bash
  sudo apt update
  sudo apt upgrade
  ```

### Installation

- Import the key that is used to sign the release
  ```bash
  wget -qO - https://ppa.hornet.zone/pubkey.txt | sudo apt-key add -
  ```
- Add the HORNET repository to your APT sources<br>
  Stable:
  ```bash
  sudo sh -c 'echo "deb http://ppa.hornet.zone stable main" >> /etc/apt/sources.list.d/hornet.list'
  ```
  Testing (incl. pre-releases):<br>
  ```bash
  sudo sh -c 'echo "deb http://ppa.hornet.zone testing main" >> /etc/apt/sources.list.d/hornet.list'
  ```
- Install HORNET:
  ```bash
  sudo apt update
  sudo apt install hornet
  ```
- Start the HORNET service with:
  ```bash
  sudo service hornet start
  ```
- Watch the logs with:
  ```bash
  sudo journalctl -u hornet.service -f
  ```
- Done

### Operation

- Stop HORNET
  - `sudo service hornet stop`
- Start HORNET
  - `sudo service hornet start`
- Watch the logs
  - `sudo journalctl -u hornet.service -f`
- Remove the mainnetdb (e.g. in case of a failure):
  1. Stop HORNET
  2. `sudo rm -r /var/lib/hornet/mainnetdb`
  3. Start HORNET

### Configuration

You can find HORNET's configuration files in:<br>
`/var/lib/hornet/`<br><br>

If you have modified the `config.json`, you have to restart HORNET:<br>
`sudo service hornet stop && sudo service hornet start`<br>
or<br>
`sudo service hornet restart`
