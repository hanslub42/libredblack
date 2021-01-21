# libredblack

Copy of Damian Ivereigh's RedBlack Balanced Tree Searching and Sorting
Library - http://libredblack.sourceforge.net/ After 20 years its bits
have rotten somewhat. As it is an essential part of rlwrap I (Hans Lub
hanslub42@gmail.com) will try to get it up to date

## CHANGES:

- rbgen updated to work with python 2 and 3 

## TODO:

- updating build system (`Makefile.in` and consorts) 


## Original README:

This is a small library that provides the red-black balanced tree
algorithm.  It's provided in two forms; as a linkable library and as a
code generator that can be used to create customized versions with a
simpler API and better performance.

If this code is raw out of the CVS tree, you will have to do the following to
compile it:-

sh ./autogen.sh

NOTE: When you have done a 'make install', you should check that
/etc/ld.so.conf contains the directory /usr/local/lib, and you should
also probably run /sbin/ldconfig to make sure that ld.so's cache file
is up to date.

23 May 2000
Damian Ivereigh
Cisco Systems Inc
