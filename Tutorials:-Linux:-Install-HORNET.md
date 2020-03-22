This is a small tutorial on how to install HORNET using the `.deb` package.

### Preparations

- Setup an Ubuntu server (Add a ssh key, activate a firewall,...)
- Update your system with:<br>
  ```bash
  sudo apt update
  sudo apt upgrade
  ```

### Installation

- Download the latest HORNET `.deb` package for your system from [GitHub releases](https://github.com/gohornet/hornet/releases/latest)
- Install HORNET with:
  ```bash
  sudo dpkg -i hornet_<version>_<arch>.deb
  ```
  Replace `<version>` and `<arch>` accordingly to your downloaded `.deb` package
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
`/etc/hornet/`<br><br>

If you have modified the `config.json`, you have to restart HORNET:<br>
`sudo service hornet stop && sudo service hornet start`<br>
or<br>
`sudo service hornet restart`
