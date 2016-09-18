# README

## Installation

Pull the image `timonier/tinc`:

```sh
# Get the latest image (version 1.0.28)
docker pull timonier/tinc

# Or get a specific version

# Get the version 1.0.28
docker pull timonier/tinc:1.0.28
```

## Usage

Run the application via `docker run`. The [tincd options](https://linux.die.net/man/8/tincd) can be passed as arguments:

```sh
docker run \
    --cap-add NET_ADMIN \
    --device=/dev/net/tun \
    --net host \
    -i \
    -t \
    -v /srv/tinc:/etc/tinc \
    timonier/tinc --net demo --user nobody
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
* [command "docker pull"](https://docs.docker.com/reference/commandline/pull/)
* [command "docker run"](https://docs.docker.com/reference/run/)
* [image "timonier/tinc"](https://hub.docker.com/r/timonier/tinc/)
