# README

A VPN daemon

## Installation

Copy `bin/tincd` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl --location --output /usr/local/bin/tincd "https://github.com/timonier/tinc/raw/master/bin/tincd"
sudo chmod +x /usr/local/bin/tincd
```

Linux users can use the [installer](https://github.com/timonier/tinc/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/tinc/raw/master/bin/installer" | sudo sh -s -- install
```

## Usage

Run the command `tincd`:

```sh
# See all tincd options

tincd --help

# Run tincd

tinc \
    --config /etc/tinc \
    --net demo \
    --user nobody
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [image "timonier/tinc"](https://hub.docker.com/r/timonier/tinc/)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)
* [tinc](https://www.tinc-vpn.org/)
