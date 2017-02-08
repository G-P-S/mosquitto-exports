# mosquitto-exports
prebuilt mosquitto binaries

How to linux-x64 build on Ubuntu 12.04x64
apt-get install libc-ares-dev
apt-get install uuid-dev
apt-get install xsltproc
make


## How to linux-arm-xc6 build on Ubuntu 12.04x64
```
-Have BUILD_TOOLS checked out
-Have G-P-S/ c-ares-exports checked out

in 'config.mk' disable uuid: WITH_UUID:=no
 
CC=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-objdump CFLAGS="-I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6/lib -lcares"  make

STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip make install
```

## linux-arm-ep-debug built on Ubuntu 12.04x64, mosquitto 1.4.10
```
in 'config.mk' disable uuid: WITH_UUID:=no
ex: prefix=/usr/projects/G-P-S/mosquitto-exports/linux-arm-ep-debug

CC=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-gcc CXX=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-g++ LD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld CXXLD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip AR=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ar AS=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-as NM=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-nm RANLIB=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ranlib OBJDUMP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-objdump CFLAGS="-DMQTTVERSION=\"1.4.2\" --sysroot=/root/CHP_SDK/sysroot -ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/include" LDFLAGS="--sysroot=/root/CHP_SDK/sysroot -L/root/CHP_SDK/sysroot/usr/lib -L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/lib -lcares -lssl"  make  
```

## linux-arm-ep-release built on Ubuntu 12.04x64, mosquitto 1.4.10
```
in 'config.mk' set prefix to install dir
ex: prefix=/usr/projects/G-P-S/mosquitto-exports/linux-arm-ep-release

CC=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-gcc CXX=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-g++ LD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld CXXLD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip AR=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ar AS=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-as NM=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-nm RANLIB=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ranlib OBJDUMP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-objdump CFLAGS="-DMQTTVERSION=\"1.4.2\" --sysroot=/root/CHP_SDK/sysroot -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/include" LDFLAGS="--sysroot=/root/CHP_SDK/sysroot -L/root/CHP_SDK/sysroot/usr/lib -L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/lib -lcares -lssl"  make

STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip make install
```
