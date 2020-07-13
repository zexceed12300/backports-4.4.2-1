## HowTo Build
### Preparing
```
export ARCH=arm64
export CROSS_COMPILE=/usr/bin/aarch64-linux-gnu
export KLIB=/lib/modules/$(uname -r)
```
ARCH is your device architecture. 
CROSS_COMPILE is GCC Toolchain(aarch64-linux-gnu for arm64, arm-linux-gnueabihf for armhf).
KLIB is path to kernel libraries. make sure you have installed kernel headers.

### Building
1. Enable your drivers
```
make menuconfig
```
Or you can enable drivers by defconfig. look at defconfigs folder
```
make defconfigs-[suffix defconfigs name]
```
### Compiling 
```
make
```
if there is no error or success you will see a .ko file spread in this directory. you can diirectly load the driver using insmod

### Installing
```
make install
```
your drivers will be installed at /lib/modules/$(uname -r)/kernel. load the driver using modprobe
