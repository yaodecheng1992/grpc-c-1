# GRPC-C

C implementation of [gRPC](http://www.grpc.io/) layered of top of core libgrpc. 

## Prerequisites

Make sure you have the following install in order to install dependencies

```
apt install -y autoconf automake libtool curl make g++ unzip zlib1g-dev zlib1g openssl libssl-dev libc-ares-dev libc-ares2 pkg-config
```

## Build

```sh
export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
autoreconf --install
git submodule update --init
./builddeps.sh
mkdir build && cd build
../configure
make
sudo make install
```

If you want to install dependencies in a different directory other than /usr/local/, use ./buildgen.sh <your-prefix>


## Examples

```sh
cd build/examples
make gencode
make
```

This should build foo_client and foo_server. To run example code, 

```sh
sudo ./foo_server test
sudo ./foo_client test
```

## Status

Pre-alpha. Under active development. APIs may change.

## Dependencies

- gRPC [v1.3.0](https://github.com/grpc/grpc/releases/tag/v1.3.0)
- protobuf 3.0
- protobuf-c 1.2.1
