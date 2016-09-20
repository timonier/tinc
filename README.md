# README

## Installation

Copy the script `bin/tincd` into your executable folder (like `/usr/local/bin` or `$HOME/bin`).

```sh
sudo curl -sLo /usr/local/bin/tincd "https://github.com/timonier/tinc/raw/master/bin/tincd"
sudo chmod +x /usr/local/bin/tincd
```

Linux users can use the [installer](https://github.com/timonier/tinc/blob/master/bin/installer):

```sh
curl -sL "https://github.com/timonier/tinc/raw/master/bin/installer" | sudo sh -s install
```

## Usage

Run the script via `tincd`.

```sh
tincd --net demo --user nobody
```

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [tinc](https://www.tinc-vpn.org/)
* [tincd options](https://linux.die.net/man/8/tincd)
* [image "timonier/tinc"](https://hub.docker.com/r/timonier/tinc/)
