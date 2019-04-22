## Aleth – Ethereum C++ client, tools and libraries 

### Build instructions
```sh
$ git clone --recursive https://github.com/ethereum/aleth.git
$ cd aleth
$ mkdir build; cd build
$ cmake --build .
```

### Common env variable

CC="path to clang"
CXX="path to clang++"
CFLAGS="-O3"
CXXFLAGS="-O3"

### updated env variable while benchmarking

CFLAGS="-O3 -mllvm -enable-gvn-hoist=true -mllvm -simplifycfg-sink-common=false -mllvm -debug-only=gvn-hoist"
CXXFLAGS="-O3 -mllvm -enable-gvn-hoist=true -mllvm -simplifycfg-sink-common=false -mllvm -debug-only=gvn-hoist"
