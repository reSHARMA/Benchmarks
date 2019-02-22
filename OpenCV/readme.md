# Open CV

## Building

```sh
git clone https://github.com/opencv/opencv.git
```

With clang-8,

```sh
$ mkdir build
$ cd build
$ cmake -D CMAKE_BUILD_TYPE=Release  -DCMAKE_CXX_COMPILER=<path to clang++> -DCMAKE_CC_COMPILER=<path to clang>  -DBUILD_EXAMPLES=ON  -DWITH_CUDA=OFF -DWITH_OPENCL=OFF -DWITH_IPP=OFF ..
$ make VERBOSE=1 -j7
```

With enabled gvn hoist pass,

```sh
$ mkdir build
$ cd build
$ cmake -D CMAKE_BUILD_TYPE=Release  -DCMAKE_CXX_COMPILER=<path to clang++> -DCMAKE_CC_COMPILER=<path to clang> -DCMAKE_CXX_FLAGS="-mllvm -enable-gvn-hoist=true -mllvm -simplifycfg-sink-common=false" -DCMAKE_C_FLAGS="-mllvm -enable-gvn-hoist=true -mllvm -simplifycfg-sink-common=false" -DBUILD_EXAMPLES=ON  -DWITH_CUDA=OFF -DWITH_OPENCL=OFF -DWITH_IPP=OFF ..
$ make VERBOSE=1 -j7
```

[Reference](https://docs.opencv.org/trunk/d7/d9f/tutorial_linux_install.html)

## Measuring size

#### 1. As described at [Compact build advice](https://github.com/opencv/opencv/wiki/Compact-build-advice#results)

```sh
$ du -hc build/bin/example_cpp* | grep total
```

#### 2. Measuring size individually at build/lib and build/bin

## Performance benchmarking

```sh
$ python <root_for_opencv_source>/modules/ts/misc/run.py <path_to_opencv_build>
```

Run perf test for both the builds. For every test suite example core.

```sh
$ mkdir test && cd test
$ cp <path_to_build1>/*core*xml ./
$ cp <path_to_build2>/*core*xml ./
$ python <root_for_opencv_source>/modules/ts/misc/run.py ./*xml -o txt > result.txt
```


