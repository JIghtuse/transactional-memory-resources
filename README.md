Transactional memory
====================

Transactional memory is a technique attempts to simplify concurrent
programming, allowing group of load and store instructions to execute in an
atomic way.

Implementations
===============

* VELOX project
    * [official site](http://www.velox-project.eu/)
* C/C++ proposal to language modifications
    * [tmforcplusplus](https://sites.google.com/site/tmforcplusplus/)
* Intel prototype compiler
    * [stm-compiler](http://software.intel.com/en-us/articles/intel-c-stm-compiler-prototype-edition/)
* G++ 4.7 (GNU C++ Compiler) supports STM.
    * [linux.conf.au 2013 (Video)](http://youtu.be/y906i0xtP8E)
    * [linux.conf.au 2013 slides](http://www-users.cs.umn.edu/~boutcher/stm/)
    * [linux.conf.au 2014 (Video)](http://mirror.linux.org.au/pub/linux.conf.au/2014/Friday/105-Whats_the_deal_with_Hardware_Transactional_Memory_-_Michael_Neuling.mp4)
    * [Transactional Memory](http://gcc.gnu.org/wiki/TransactionalMemory)
    * [TM Intrinsics](http://gcc.gnu.org/onlinedocs/gcc/X86-transactional-memory-intrinsics.html)
    * [tutorial](http://pmarlier.free.fr/gcc-tm-tut.html)
* Clojure has STM support built into the core language
    * [Clojure STM - What? Why? How?](http://sw1nn.com/blog/2012/04/11/clojure-stm-what-why-how/)
    * [Some Clojure STM features](http://stackoverflow.com/a/4561205/1145239)
* Common Lisp
    * [cl-stm](http://common-lisp.net/project/cl-stm/)
* Haskell: STM and DSTM libraries
    * [STM](http://www.haskell.org/haskellwiki/Software_transactional_memory)
    * [realwordhaskell STM](http://book.realworldhaskell.org/read/software-transactional-memory.html)
* Python
    * [Durus](http://www.mems-exchange.org/software/DurusWorks/)
* Java/Scala
    * [scala-stm](http://nbronson.github.io/scala-stm/)

Hardware support
================

* Intel Haswell architecture
    * [haskell-tm](http://www.realworldtech.com/haswell-tm/)
    * [intel-haswll-tsx](http://www.bit-tech.net/news/hardware/2012/02/09/intel-haswell-tsx/)
* IBM Power8
    * [IBM STM](http://arstechnica.com/gadgets/2011/08/ibms-new-transactional-memory-make-or-break-time-for-multithreaded-revolution/)
    * [IBM Power8](http://forums.theregister.co.uk/forum/1/2013/08/27/ibm_power8_server_chip/)

Successful migration/using
==========================

* [Early Experience with a Commercial Hardware Transactional Memory Implementation](http://www.cse.iitd.ac.in/~sbansal/csl862-os/readings/htm_experiences.pdf)
* [Transactionalizing Legacy Code: An Experience Report Using GCC and Memcached](http://transact2013.cse.lehigh.edu/vyas.pdf)
* [Software Transactional Memory in the Linux Kernel](http://cs.brown.edu/research/pubs/theses/ugrad/2012/bressler.pdf)
* [Performance Characteristics of Hardware Transactional Memory for Molecular Dynamics Application on BlueGene/Q](http://cacs.usc.edu/papers/PDSEC13-mkunaseth-HTM.pdf)
* [Evaluation of Blue Gene/Q Hardware Support for Transactional Memories](http://researcher.ibm.com/researcher/files/us-pengwu/BGQPerfPaper-final-PACT12.pdf)

Works
=====

* An architecture for mostly functional languages, Tom Knight, 1986.
* Impossibility and Universality Results for Wait-Free Synchronization, Herlihy, 1988.
* A Methodology for Implementing Highly Concurrent Data Structures, Herlihy, 1990.
* Wait-Free Synchronization, Herlihy, 1991.
* A Methodology for Implementing Highly Concurrent Data Objects, Herlihy, 1993.
* Software Transactional Memory, Nir Shavit and Dan Toutiou, 1997.
* A Practical Multi-Word Compare-and-Swap Operation, Harris, Fraser, Pratt, 2002.
* Practical Lock-Free and Wait-Free LL:SC:VL Implementations Using 64-bit CAS, Michael, 2004.
* The Art of Multiprocessor Programming, Herlihy, Shavit, 2008
* [Transactional memory: architectural support for lock-free data structures](http://cs.brown.edu/~mph/HerlihyM93/herlihy93transactional.pdf)
* [TxLinux: using and managing hardware transactional memory in an operating system](http://academic.research.microsoft.com/Paper/4122780.aspx)
* [Patrick Marlier publications](http://pmarlier.free.fr/cv.html)
* [Simon Peyton Jones pulications](https://research.microsoft.com/en-us/um/people/simonpj/papers/stm/)
* [Andi Kleen works](http://halobates.de/)

Materials/Links
===============

* [TRANSACT workshop 2012](http://transact2012.cse.lehigh.edu/)
* [TRANSACT workshop 2013](http://transact2013.cse.lehigh.edu/)
* [TM/STM bibliography](http://research.cs.wisc.edu/trans-memory/biblio/index.html)
* [MSDN](http://blogs.msdn.com/b/devdev/archive/2005/10/20/483247.aspx)
* [SO answer explaining TM](http://stackoverflow.com/questions/11255640/what-is-transactional-memory)
