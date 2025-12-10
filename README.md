# vyos-build-arm64
vyos-build-arm64

To build VyOS-arm64:
```
git clone https://github.com/vyos-vyos-build
git clone https://github.com/sever-sever/vyos-build-arm64
rsync -avh vyos-build-arm64/data/build-flavors/ vyos-build/data/build-flavors/

cd vyos-build
./build-vyos-image --architecture arm64 generic-arm64
```
