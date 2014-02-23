Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2014 Amigacoin Developers

Distributed under the MIT/X11 software license, see the accompanying
file COPYING or http://www.opensource.org/licenses/mit-license.php.
This product includes software developed by the OpenSSL Project for use in the [OpenSSL Toolkit](http://www.openssl.org/). This product includes
cryptographic software written by Eric Young ([eay@cryptsoft.com](mailto:eay@cryptsoft.com)), and UPnP software written by Thomas Bernard.


See readme-qt.rst for instructions on building Amigacoin-Qt, the
graphical user interface.

WINDOWS BUILD NOTES
===================

Compilers Supported
-------------------
TODO: What works?
Note: releases are cross-compiled using mingw running on Linux.


Dependencies
------------
Libraries you need to download separately and build:

                default path               download
OpenSSL         \openssl-1.0.1f-mgw        http://www.openssl.org/source/
Berkeley DB     \db-5.1.29.NC-mgw          http://www.oracle.com/technology/software/products/berkeley-db/index.html
Boost           \boost-1.55.0-mgw          http://www.boost.org/users/download/
miniupnpc       \miniupnpc-1.9-mgw         http://miniupnp.tuxfamily.org/files/

Their licenses:

	OpenSSL        Old BSD license with the problematic advertising requirement
	Berkeley DB    New BSD license with additional requirement that linked software must be free open source
	Boost          MIT-like license
	miniupnpc      New (3-clause) BSD license

Versions used in this release:

	OpenSSL      1.0.1f
	Berkeley DB  5.1.29.NC
	Boost        1.55.0
	miniupnpc    1.9


OpenSSL
-------
MSYS shell:

un-tar sources with MSYS 'tar xfz' to avoid issue with symlinks (OpenSSL ticket 2377)
change 'MAKE' env. variable from 'C:\MinGW32\bin\mingw32-make.exe' to '/c/MinGW32/bin/mingw32-make.exe'

	cd /c/openssl-1.0.1f
	./config
	make

Berkeley DB
-----------
MSYS shell:

	cd /c/db-5.1.29.NC/build_unix
	sh ../dist/configure --disable-replication --enable-mingw --enable-cxx
	make

Boost
-----
DOS prompt:

	cd \boost_1_55_0
	bootstrap.bat mingw
	b2 --build-type=complete --with-chrono --with-filesystem --with-program_options --with-system --with-thread toolset=gcc stage

MiniUPnPc
---------
UPnP support is optional, make with `USE_UPNP=` to disable it.

MSYS shell:

	cd /c/miniupnpc
	make -f Makefile.mingw
	mkdir miniupnpc
	cp *.h miniupnpc/

leveldb
-------
MSYS shell:

	cd /amigacoin/src/leveldb/
	export TARGET_OS=NATIVE_WINDOWS
	make libleveldb.a libmemenv.a

Amigacoin
---------
DOS prompt:

	cd \amigacoin\src
	mingw32-make -f makefile.mingw
	strip amigacoind.exe
