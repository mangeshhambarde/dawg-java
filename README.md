dawg-java
=========

DAWGs (directed acyclic word graphs) are minimal, highly compressed dictionaries implemented using deterministic acyclic finite state automata, providing lightning fast lookup speeds.

This Java class provides read-only access to files created by the [dawgdic] (https://code.google.com/p/dawgdic) C++ library and [DAWG] (https://github.com/kmike/DAWG) Python module.

Building in C++
---------------
A single C++ source file "dawgdic-build.cpp" which uses the dawgdic library is included in this package to build a dawg from a lexicon file, which has **sorted** lexicons separated by **line feeds** (not CRLF), and write it to disk. This code is not rigorously tested, so may give nasty suprises or fail miserably.

	g++ -O3 dawgdic-build.cc -o dawgdic-build
	dawgdic-build lexicons.txt dawg.bin


Building in Python
------------------
Using the DAWG module, building the dawg is as simple as

	import dawg
	d = dawg.DAWG(data)
	d.save('words.dawg')
