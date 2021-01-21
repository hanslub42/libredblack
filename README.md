# libredblack

Copy of Damian Ivereigh's RedBlack Balanced Tree Searching and Sorting
Library - http://libredblack.sourceforge.net/ After 20 years its bits
have rotten somewhat. As it is an essential part of
link:https://github.com/hanslub42/rlwrap[rlwrap] it is kept up-to-date
by the rlwrap maintainer.



## What are red-black trees?

A kind of binary trees that are guaranteed to not become too
unbalanced.  Search, insertion and deletion are O(log(n)). See
link:https://en.wikipedia.org/wiki/Red%E2%80%93black_tree[Wikipedia].
This package implements `rbgen`, a simple kind of code generator that
emits C-code specialized for an user-specified data type.


## CHANGES:

- rbgen updated to work with python 2 and 3 
- build system updated (`configure.ac`, `Makefile.am` and consorts) 
- removed auto-generated files (like `configure`, `Makefile.in`)


## INSTALLATION

see the INSTALL file. 

## Original README:

This is a small library that provides the red-black balanced tree
algorithm.  It's provided in two forms; as a linkable library and as a
code generator that can be used to create customized versions with a
simpler API and better performance.

[...] 

NOTE: When you have done a 'make install', you should check that
/etc/ld.so.conf contains the directory /usr/local/lib, and you should
also probably run /sbin/ldconfig to make sure that ld.so's cache file
is up to date.

23 May 2000
Damian Ivereigh
Cisco Systems Inc
