# ZeroMQ OpenWRT Makefile collection

A Makefile collection to be used in OpenWRT builds as package Makefiles.
Enables you to select the packages in the menuconfig and build them appropriately.
Have been tested on several boxes as properly working, so far:

* MIPS - RT305x chip
* MIPS - AR7x/AR9x chips

## Naming a cat like a dog

All those 3 libraries contains /usr/lib/lib*.so files:

zeromq == libzmq.git
czmq == libczmq.git
zyre == zyre.git

DeMidi is one example application which depends on those 3 libraries.

## License

MIT
