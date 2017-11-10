# mosquitto-exports
prebuilt mosquitto binaries
repo: https://github.com/eclipse/mosquitto.git

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

## linux-arm-a53-debug  mosquitto 1.4.10
```
in 'config.mk' set prefix to install dir, which should be the path to mosquitto-exports
and set WITH_DOCS:=no
ex: prefix=/home/path/to/mosquitto-exports/linux-arm-a53-debug

CC=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-gcc CXX=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-g++ LD=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ld CXXLD=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ld STRIP=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-strip AR=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ar AS=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-as NM=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-nm RANLIB=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ranlib OBJDUMP=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-objdump CFLAGS="-DMQTTVERSION=\"1.4.2\" --sysroot=/opt/tas_sdk/sysroots -ggdb -I`pwd`/../c-ares-exports/linux-arm-a53-debug/include -I`pwd`/../openssl-exports/linux-arm-a53-debug/include" LDFLAGS="--sysroot=/opt/tas_sdk/sysroots -L/opt/tas_sdk/sysroots/usr/lib -L`pwd`/../c-ares-exports/linux-arm-a53-debug/lib -L`pwd`/../openssl-exports/linux-arm-a53-debug/lib -lcares -lssl"  make

#Note:If you encounter permission issues with the make install. You may have to set the variable DESTDIR in the top level Makefile of the mosquitto repo.
STRIP=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-strip make install

manually copy lib/libmosquitto.a into exports lib dir
```
## linux-arm-a53-release  mosquitto 1.4.10
```
in 'config.mk' set prefix to install dir, which should be the path to mosquitto-exports
and set WITH_DOCS:=no
ex: prefix=/home/path/to/mosquitto-exports/linux-arm-a53-release

CC=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-gcc CXX=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-g++ LD=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ld CXXLD=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ld STRIP=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-strip AR=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ar AS=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-as NM=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-nm RANLIB=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-ranlib OBJDUMP=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-objdump CFLAGS="-DMQTTVERSION=\"1.4.2\" --sysroot=/opt/tas_sdk/sysroots -ggdb -I`pwd`/../c-ares-exports/linux-arm-a53-release/include -I`pwd`/../openssl-exports/linux-arm-a53-release/include" LDFLAGS="--sysroot=/opt/tas_sdk/sysroots -L/opt/tas_sdk/sysroots/usr/lib -L`pwd`/../c-ares-exports/linux-arm-a53-release/lib -L`pwd`/../openssl-exports/linux-arm-a53-release/lib -lcares -lssl"  make

#Note:If you encounter permission issues with the make install. You may have to set the variable DESTDIR in the top level Makefile of the mosquitto repo.
STRIP=/opt/tas_sdk/sysroots/x86_64-linux/usr/bin/arm-oemllib32-linux-gnueabi/arm-oemllib32-linux-gnueabi-strip make install

manually copy lib/libmosquitto.a into exports lib dir
```
