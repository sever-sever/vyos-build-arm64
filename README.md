# vyos-build-arm64
vyos-build-arm64

To build VyOS arm64 needs an additional steps:
```
docker pull vyos/vyos-build:current-arm64
git clone -b current --single-branch https://github.com/vyos/vyos-build
cd vyos-build

docker run --rm -it --privileged --sysctl net.ipv6.conf.lo.disable_ipv6=0 -v $(pwd):/vyos -w /vyos vyos/vyos-build:current-arm64 bash

# Add required telegraf key
wget -q https://repos.influxdata.com/influxdata-archive_compat.key

sudo ./build-vyos-image iso \
  --architecture arm64 \
  --custom-apt-entry "deb [arch=arm64] https://repos.influxdata.com/debian/ bookworm stable" \
  --custom-apt-key /vyos/influxdata-archive_compat.key
```
