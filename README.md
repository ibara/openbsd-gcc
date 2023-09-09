OpenBSD GCC
===========
This repository contains packages of
[GCC](https://gcc.gnu.org/)
and
[binutils](https://www.gnu.org/software/binutils/)
for
[OpenBSD](https://www.openbsd.org/).

These packages are built from the development trees for both
GCC and binutils. The date on the package name is also the
date of git tree checkout.

These packages are for people who need a more up-to-date GCC
than official packages provide. This version of GCC includes
compilers for
[Ada](https://en.wikipedia.org/wiki/Ada_%28programming_language%29),
[C](https://en.wikipedia.org/wiki/C_%28programming_language%29),
[C++](https://en.wikipedia.org/wiki/C%2B%2B),
[D](https://dlang.org/),
[Fortran](https://fortran-lang.org/en/),
[Modula-2](https://en.wikipedia.org/wiki/Modula-2),
[Objective-C](https://en.wikipedia.org/wiki/Objective-C),
[Objective-C++](https://en.wikipedia.org/wiki/Objective-C#Objective-C++),
and
[Rust](https://www.rust-lang.org/).

This package depends only on base system libraries.

The compiler and utilities installs into `/usr/local/gnu/bin`
to prevent conflicts with the official GCC packages.

This package also contains the following binutils utilities:
* addr2line
* ar
* as
* c++filt
* elfedit
* gprof
* nm
* objcopy
* objdump
* ranlib
* readelf
* size
* strings
* strip

GCC is set to use the GNU as included in this package as its
assembler. This guarantees the latest metadata support. It
also proves the best matching for `-march=native` compiles.

Why?
----
I needed them, so perhaps other people need them too. There's
no rule that says you have to use this.

How?
----
To go the
[releases](https://github.com/ibara/openbsd-gcc/releases)
page. Each CPU architecture has its own tag. Select the tag
appropriate for the machine you want to install on.

Alternatively, you could run a command such as:
```
$ doas pkg_add -Dunsigned https://github.com/ibara/openbsd-gcc/releases/download/`uname -m`/gcc-devel-14.0.0pl`date +%Y%m%d`.tgz
```
Where `date +%Y%m%d` is the date code for the package.

Caveats
-------
GCC may not have all the security mitigations the in-base
[clang](https://clang.llvm.org/)
provides, such as
[Retguard](https://www.openbsd.org/papers/eurobsdcon2018-rop.pdf).

License
-------
[GPLv3 or later](https://www.gnu.org/licenses/gpl-3.0.en.html)

[GCC Runtime Library Exception](https://www.gnu.org/licenses/gcc-exception-3.1)
