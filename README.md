# mosquitto-exports
prebuilt mosquitto binaries

#How to linux-x64-release build on Ubuntu 12.04x64
apt-get install libc-ares-dev
apt-get install uuid-dev
apt-get install xsltproc
make CFLAGS="-O3"

#linux-x64-debug
make CFLAGS="-ggdb"

#How to linux-arm-xc6-release build on Ubuntu 12.04x64
#-Have BUILD_TOOLS checked out
#-Have G-P-S/ c-ares-exports and openssl checked out

#in 'config.mk' disable uuid: WITH_UUID:=no
 
CC=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-objdump CFLAGS="-O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-release/lib -lcares -lssl"  make

#linux-arm-xc6-debug
CC=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-objdump CFLAGS="-ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-debug/lib -lcares -lssl"  make

#How to linux-arm-a7-release build on Ubuntu 12.04x64
#-Have BUILD_TOOLS checked out
#-Have G-P-S/ c-ares-exports and openssl checked out

#in 'config.mk' disable uuid: WITH_UUID:=no
CC=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-objdump CFLAGS="-O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-release/lib -lcares -lssl"  make
 

#linux-arm-a7-debug
CC=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-objdump CFLAGS="-ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-debug/lib -lcares -lssl"  make

#How to linux-arm-a9-release build on Ubuntu 12.04x64
#-Have BUILD_TOOLS checked out
#-Have G-P-S/ c-ares-exports and openssl checked out

#in 'config.mk' disable uuid: WITH_UUID:=no
CC=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-objdump CFLAGS="-O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-release/lib -lcares -lssl"  make


#linux-arm-a9-debug
CC=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-objdump CFLAGS="-ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-debug/lib -lcares -lssl"  make

#linux-arm-a9s-release
#in 'config.mk' disable uuid: WITH_UUID:=no
CC=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-objdump CFLAGS="-DMQTTVERSION='\"1.4.2\"' -O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-release/lib -lcares -lssl"  make


#linux-arm-a9s-debug
CC=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-objdump CFLAGS="-DMQTTVERSION='\"1.4.2\"' -ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-debug/lib -lcares -lssl"  make

## linux-arm-ep-debug built on Ubuntu 12.04x64, mosquitto 1.4.10
```
in 'config.mk' set prefix to install dir
and set WITH_DOCS:=no
ex: prefix=/usr/projects/G-P-S/mosquitto-exports/linux-arm-ep-debug

CC=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-gcc CXX=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-g++ LD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld CXXLD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip AR=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ar AS=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-as NM=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-nm RANLIB=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ranlib OBJDUMP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-objdump CFLAGS="-DMQTTVERSION=\"1.4.2\" --sysroot=/root/CHP_SDK/sysroot -ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/include" LDFLAGS="--sysroot=/root/CHP_SDK/sysroot -L/root/CHP_SDK/sysroot/usr/lib -L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/lib -lcares -lssl"  make  

STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip make install

manually copy lib/libmosquitto.a into exports lib dir
```

## linux-arm-ep-release built on Ubuntu 12.04x64, mosquitto 1.4.10
```
in 'config.mk' set prefix to install dir
and set WITH_DOCS:=no
ex: prefix=/usr/projects/G-P-S/mosquitto-exports/linux-arm-ep-release

CC=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-gcc CXX=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-g++ LD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld CXXLD=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ld STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip AR=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ar AS=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-as NM=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-nm RANLIB=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-ranlib OBJDUMP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-objdump CFLAGS="-DMQTTVERSION=\"1.4.2\" --sysroot=/root/CHP_SDK/sysroot -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/include" LDFLAGS="--sysroot=/root/CHP_SDK/sysroot -L/root/CHP_SDK/sysroot/usr/lib -L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-ep-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-ep-debug/lib -lcares -lssl"  make

STRIP=/root/CHP_SDK/cross_compile/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-strip make install

manually copy lib/libmosquitto.a into exports lib dir
```

