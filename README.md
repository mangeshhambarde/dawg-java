dawg-java
=========

DAWGs are minimal, highly compressed directed acyclic word graphs especially for static data, providing lightning fast lookup speeds.

This Java class provides read-only access to files created by the `dawgdic`_ C++ library and `DAWG`_ Python module.

.. _dawgdic: https://code.google.com/p/dawgdic/
.. _DAWG: https://github.com/kmike/DAWG

Documentation
=============

Building in C++
---------------
A single C++ source file "dawgdic-build.cc" from the dawgdic library is included in this package to build a dawg from a lexicon file, which has lexicons separated by newlines, and write it to disk. Please take care of different newline conventions to avoid nasty surprises.

	g++ -O3 dawgdic-build.cc -o dawgdic-build
	dawgdic-build lexicons.txt dawg.bin


Building in Python
------------------
Building the dawg is as simple as

	import dawg
	d = dawg.DAWG(data)
	d.save('words.dawg')