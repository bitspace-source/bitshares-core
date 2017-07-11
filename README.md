DAJIE Core
==============
* [Getting Started](#getting-started)

DAJIE Core is the DAJIE blockchain implementation and command-line interface.

Getting Started
---------------
We recommend building on Ubuntu 16.04 LTS, and the build dependencies may be installed with:

    sudo apt-get update
    sudo apt-get install autoconf cmake git libboost-all-dev libssl-dev build-essential ncurses-dev libbz2-dev libreadline-dev

To build after all dependencies are installed:

    git clone git@github.com:bitspace-source/dajie-core.git
    cd dajie-core
    git submodule update --init --recursive
    cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo .
    make

**NOTE:** DAJIE requires an [OpenSSL](https://www.openssl.org/) version in the 1.0.x series. OpenSSL 1.1.0 and newer are NOT supported. If your system OpenSSL version is newer, then you will need to manually provide an older version of OpenSSL and specify it to CMake using `-DOPENSSL_INCLUDE_DIR`, `-DOPENSSL_SSL_LIBRARY`, and `-DOPENSSL_CRYPTO_LIBRARY`.

**NOTE:** DAJIE requires a [Boost](http://www.boost.org/) version in the range [1.57, 1.60]. Versions earlier than
1.57 or newer than 1.60 are NOT supported. If your system Boost version is newer, then you will need to manually build
an older version of Boost and specify it to CMake using `DBOOST_ROOT`.

After building, the witness node can be launched with:

    ./programs/witness_node/witness_node
