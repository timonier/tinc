# README

A VPN daemon

⚠️ This project is no longer maintained. ⚠️

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/tinc/raw/master/bin/installer" | sudo sh -s -- install
```

__Note__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

## Usage

Run the command `tincd`:

```sh
# See all tincd options

tincd --help

# Run tincd

tinc --config /etc/tinc --net demo --user nobody
```

## Links

* [image "timonier/tinc"](https://hub.docker.com/r/timonier/tinc/)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
* [tinc](https://www.tinc-vpn.org/)
