# Simple container running `dnsmasq`

The daemon will read all files in the volume mounted to `/dnsmasq.hosts`

```
$ docker run \
    --name dnsmasq \
    -v $(pwd)/dnsmasq.hosts:/dnsmasq.hosts \
    -p 127.0.0.10:53:2053/udp \
    -d gbraad/dnsmasq
```

Overwrite the used configuration

```
$ docker run \
    --name dnsmasq \
    -v $(pwd)/dnsmasq.conf:/etc/dnsmasq.conf \
    -p 127.0.0.10:53:2053/udp \
    -d gbraad/dnsmasq
```

