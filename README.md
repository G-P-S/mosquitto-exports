# mosquitto-exports
prebuilt mosquitto binaries

## How to build linux-x64-release on Ubuntu 12.04x64
```
apt-get install libc-ares-dev
apt-get install uuid-dev
apt-get install xsltproc
make CFLAGS="-O3"
```

## How to build linux-x64-debug
Same as above but with
```
make CFLAGS="-ggdb"
```

## How to build linux-arm-xc6-release on Ubuntu 12.04x64
pre-requisites:
- Have BUILD_TOOLS checked out
- Have G-P-S/c-ares-exports and openssl checked out
- in 'config.mk' disable uuid: WITH_UUID:=no
 
```
CC=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-objdump CFLAGS="-O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-release/lib -lcares -lssl"  make
```

## How to build linux-arm-xc6-debug
```
CC=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/gcc-linaro-arm-linux-gnueabihf-4.7-2012.11-20121123_linux/bin/arm-linux-gnueabihf-objdump CFLAGS="-ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-xc6-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-xc6-debug/lib -lcares -lssl"  make
```

## How to build linux-arm-a7-release on Ubuntu 12.04x64
pre-requisites:
- Have BUILD_TOOLS checked out
- Have G-P-S/ c-ares-exports and openssl checked out
- in 'config.mk' disable uuid: WITH_UUID:=no

```
CC=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-objdump CFLAGS="-O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-release/lib -lcares -lssl"  make
``` 

## How to build linux-arm-a7-debug
``` 
CC=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2009q3/bin/arm-none-linux-gnueabi-objdump CFLAGS="-ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a7-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a7-debug/lib -lcares -lssl"  make
``` 

## How to build linux-arm-a9-release on Ubuntu 12.04x64
pre-requisites:
- Have BUILD_TOOLS checked out
- Have G-P-S/ c-ares-exports and openssl checked out
- in 'config.mk' disable uuid: WITH_UUID:=no

```
CC=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-objdump CFLAGS="-O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-release/lib -lcares -lssl"  make
```

## How to build linux-arm-a9-debug
```
CC=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-gcc CXX=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-g++ LD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld CXXLD=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ld STRIP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-strip AR=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ar AS=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-as NM=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-nm RANLIB=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-2012.03/bin/arm-none-linux-gnueabi-objdump CFLAGS="-ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9-debug/lib -lcares -lssl"  make
```

## How to build linux-arm-a9s-release
pre-requisites:
- in 'config.mk' disable uuid: WITH_UUID:=no

```
CC=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-objdump CFLAGS="-DMQTTVERSION='\"1.4.2\"' -O3 -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-release/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-release/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-release/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-release/lib -lcares -lssl"  make
```

## How to build linux-arm-a9s-debug
```
CC=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-gcc CXX=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-g++ LD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld CXXLD=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ld STRIP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-strip AR=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ar AS=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-as NM=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-nm RANLIB=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-ranlib OBJDUMP=/opt/BUILD_TOOLS/arm-a9s/bin/arm-linux-gnueabihf-objdump CFLAGS="-DMQTTVERSION='\"1.4.2\"' -ggdb -I/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-debug/include -I/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-debug/include" LDFLAGS="-L/usr/projects/G-P-S/c-ares/c-ares-exports/linux-arm-a9s-debug/lib -L/usr/projects/G-P-S/openssl/openssl-exports/linux-arm-a9s-debug/lib -lcares -lssl"  make
```

## How to build windows-x64
- Run cmake
- Disable SRV
- Set openssl libs to absolute directory ../../openssl/x64/Release_2013/libeay32.lib (example)
- Generate native compiler VS2013 x64 solution.
- Open and build.

## How to build osx
Modify `CMakeLists.txt` to look for openssl in the prebuilt location
```
if (${WITH_TLS} STREQUAL ON)
    if (APPLE)
        set(OPENSSL_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../openssl-exports/osx-x64-release/include)
        set(OPENSSL_CRYPTO_LIBRARY ${CMAKE_CURRENT_SOURCE_DIR}/../openssl-exports/osx-x64-release/lib/libcrypto.dylib)
        set(OPENSSL_SSL_LIBRARY ${CMAKE_CURRENT_SOURCE_DIR}/../openssl-exports/osx-x64-release/lib/libssl.dylib)
        set(OPENSSL_LIBRARIES ${OPENSSL_SSL_LIBRARY} ${OPENSSL_CRYPTO_LIBRARY})
    else()
        find_package(OpenSSL REQUIRED)
    endif()

```

Then build properly

```
cd mosquitto
mkdir build
cd build
CFLAGS=-mmacosx-version-min=10.8 cmake -DWITH_SRV=NO ..
CFLAGS=-mmacosx-version-min=10.8 make
```

