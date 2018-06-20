=================================
Installing the RecordsKeeper Node
=================================


Versioning
----------

RecordsKeeper nodes follow semantic versioning, and in addition to releases development builds are made available through source code. The development builds are not guaranteed to be working and despite our best efforts they might contain undocumented and/or broken changes. We recommend using the latest release. Package installers below will use the latest release.

Linux Pre-Installation Requirements (on Ubuntu 14.04 x64)
---------------------------------------------------------
Install dependencies on your operating system.

.. note::
   You need to install apt-get or any other package manager to install the dependent libraries.

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    sudo apt-get install libboost-all-dev
    sudo apt-get install git
    sudo apt-get install software-properties-common
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

Building from Source
####################

Clone the Repository
====================

To clone the source code, execute the following command:

.. code-block:: bash

    git clone https://github.com/RecordsKeeper/recordskeeper-core.git
    cd recordskeeper-core

Compile RecordsKeeper for Ubuntu (64-bit)
=========================================

This will build rkd, rk-cli and rk-util in the src directory.

.. code-block:: bash

    ./autogen.sh
    ./configure
    make

Windows Pre-Installation Requirements (on Ubuntu 14.04 x64)
-----------------------------------------------------------
Install dependencies on your operating system.

.. note::
   You need to install apt-get or other package manager to install the dependent libraries.

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    sudo apt-get install g++-mingw-w64-i686 mingw-w64-i686-dev g++-mingw-w64-x86-64 mingw-w64-x86-64-dev curl
    sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    sudo apt-get install git
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

Building from Source
####################

Clone the Repository
====================

To clone the source code, execute the following command:

.. code-block:: bash

    git clone https://github.com/RecordsKeeper/recordskeeper-core.git
    cd recordskeeper-core

Compile RecordsKeeper for Windows (64-bit)
==========================================

This will build rkd, rk-cli and rk-util in the src directory.

.. code-block:: bash

    ./autogen.sh
    cd depends
    make HOST=x86_64-w64-mingw32 -j4
    cd ..
    ./configure --prefix=`pwd`/depends/x86_64-w64-mingw32 --enable-cxx --disable-shared --enable-static --with-pic
    make


Mac Pre-Installation Requirements (on MacOS Sierra)
---------------------------------------------------
Install dependencies on your operating system.

.. code-block:: bash

    Install XCode and XCode command line tools
    Install git from git-scm
    Install brew (follow instructions on brew.sh)
    brew install autoconf automake berkeley-db4 libtool boost@1.57 openssl pkg-config rename
    brew link boost@1.57 --force

Prepare for Static Linking
##########################

Apple does not support statically linked binaries as documented here. However, it is convenient for end-users to launch a binary without having to first install brew, a third-party system designed for developers.

To create a statically linked RecordsKeeper blockchain which only depends on default MacOS dylibs, the following steps are taken:

    * Hide the brew boost dylibs from the build system: rename -e 's/.dylib/.dylib.hidden/' /usr/local/opt/boost/lib/*.dylib

    * Hide the brew berekley-db dylibs from the build system: rename -e 's/.dylib/.dylib.hidden/' /usr/local/opt/berkeley-db@4/lib/*.dylib

    * Hide the brew openssl dylibs from the build system: rename -e 's/.dylib/.dylib.hidden/' /usr/local/opt/openssl/lib/*.dylib

The default brew cookbook for berkeley-db and boost builds static libraries, but the default cookbook for openssl only builds dylibs.

    * Tell brew to build openssl static libraries: brew edit openssl In 'def configure_args' change 'shared' to 'no-shared' brew install openssl --force

Building from Source
####################

Clone the Repository
====================

To clone the source code, execute the following command:

.. code-block:: bash

    git clone https://github.com/RecordsKeeper/recordskeeper-core.git
    cd recordskeeper-core

Compile RecordsKeeper for Mac (64-bit)
======================================
This will build rkd, rk-cli and rk-util in the src directory.

.. code-block:: bash

    export LDFLAGS=-L/usr/local/opt/openssl/lib
    export CPPFLAGS=-I/usr/local/opt/openssl/include
    ./autogen.sh
    ./configure --with-gui=no --with-libs=no --with-miniupnpc=no
    make

Clean up
========

.. code-block:: bash

    rename -e 's/.dylib.hidden/.dylib/' /usr/local/opt/berkeley-db\@4/lib/*.dylib.hidden
    rename -e 's/.dylib.hidden/.dylib/' /usr/local/opt/boost/lib/*.dylib.hidden
    rename -e 's/.dylib.hidden/.dylib/' /usr/local/opt/openssl/lib/*.dylib.hidden
    brew edit openssl
        In 'def configure_args' change 'no-shared' to 'shared'






