# Developers Wanted! #

Please feel free to experiment with the code on your own. Patches will be gladly reviewed as long as they are clean. For now, the version is pinned to PostgreSQL 8.4.1. As for Android, the build should work with any Android version.

For those interested, you should already be comfortable working (independently) with the Android codebase. Naturally, you should also have a plethora of experience building open-source software for various platforms (e.g. ARM, x86 ). Experience in C, C++, and Java as well as experience writing Makefiles is essential (keywords: GCC Manual, embedded, cross-compilation, JNI, Android Build CookBook, GNU Make Manual).

Anyone else who would like to volunteer to assist with documentation is also welcome.

# Project Status #

Currently, this code provides two binaries:
  * libpsql.so, a shared library used by the psql binary
  * psql, a text-based client interface

The dependencies of libpsql (and thus of psql) are
  * libssl, the OpenSSL secure-socket-layer library
  * libcrypto, the OpenSSL cryptographic library
  * libz, the standard Zlib compression library

All dependencies are commonly packaged in a normal Android release.

The binaries have been tested on the G1 by a third party, with a Java wrapper that simply launched a psql process, monitoring stdin and stdout. This approach, although quick and easy, is not an optimal solution. In any case, this developer was not made privy to that Java code, which is why no Java interface is currently available. It should not be terribly difficult to create a similar Java wrapper. However there are other methods to interface with Java that are more optimal in both the memory and speed sense.

  * create a JNI interface to libpsql.so ( e.g. libpsqldroid.so )
  * create a suite of Java classes to use libpsql.so via libpsqldroid.so, and ensure that the Java code is compatible with the Dalvik VM

It is quite likely that some open-source JNI/Java binding for libpsql.so already exists. So the main challenge is, similarly, to

  1. integrate that code into the Android build system
  1. ensure that all of the Java code is compatible with the Dalvik VM