Транзакционная память
=====================

Транзакционная память - механизм, упрощающий конкурентное программирование,
позволяя группам инструкций по загрузке/сохранению выполняться атомарно.

Программная транзакционная память
=================================

Программная транзакционная память - механизм, предназначенный для контроля
доступа к общей памяти в параллельных вычислениях, аналогичный транзакциям в
базах данных. Является альтернативой синхронизации, основанной на блокировках.

Производительность
==================

В отличие от техник блокировки, STM оптимистична (предполагает, что несколько
транзакций может быть проведено без взаимного влияния их друг на друга,
вследствие чего транзакции могут происходить без блокировки ресурсов, на которые
они влияют). Поток изменяет общую память независимо от того, что делают другие
потоки, записывая каждое чтение и запись в лог. После записи происходит чтение
и верификация данных (commit). Транзакция может быть прервана в любое время,
приводя к отмене предыдущих изменений. Если транзакция не может быть проведена,
она прерывается и запускается заново до успешного выполнения.

Преимущества
============

* Избавляет от проблем программирования на основе блокировок:
    * задержки, связанные с ожиданием освобождения ресурса;
	* deadlocks теперь отсутствуют как класс;
* Существенно упрощает разработку. Для синхронизации доступа к ресурсу
достаточно включить критическую секцию в транзакцию. При наличии поддержки
аппаратного обеспечения возможно отслеживание одновременного обращения к
памяти, используемой внутри и вне транзакции (устранение ошибок программиста).

Недостатки
==========
* Необходимость отмены транзакций накладывает ограничения на поведение
транзакций: они могут выполнять только операции, которые могут быть отменены.
Такие ограничения обычно обходят созданием буферов для очереди неотменяемых
операций, которые затем выполняются вне транзакций. В Haskell такие
ограничения форсируются на стадии компиляции системой типов;
* Цена непредусмотренной коллизии может быть высока;
* Накладные расходы на мониторинг памяти при транзакциях (желательно делать
меньше операций в транзакциях;
* Сложность отладки: невозможно зайти в блок транзакции без вмешательства в
память.

Реализации
==========

* VELOX project
    * [официальный сайт](http://www.velox-project.eu/)
* C/C++ proposal to language modifications
[tmforcplusplus](https://sites.google.com/site/tmforcplusplus/)
* Intel prototype compiler
[stm-compiler](http://software.intel.com/en-us/articles/intel-c-stm-compiler-prototype-edition/)
* G++ 4.7 (GNU C++ Compiler) поддерживает STM.
    * [linux.conf.au 2013 (Video)](http://youtu.be/y906i0xtP8E)
	* [linux.conf.au 2013 slides](http://www-users.cs.umn.edu/~boutcher/stm/)
	* [Transactional Memory](http://gcc.gnu.org/wiki/TransactionalMemory)
	* [TM Intrinsics](http://gcc.gnu.org/onlinedocs/gcc/X86-transactional-memory-intrinsics.html)
	* [tutorial](http://pmarlier.free.fr/gcc-tm-tut.html)
* Clojure: поддержка встроена в ядро языка
* Common Lisp
[cl-stm](http://common-lisp.net/project/cl-stm/)
* Haskell: библиотека STM и DSTM, часть Haskell Platform
    * [STM](http://www.haskell.org/haskellwiki/Software_transactional_memory)
	* [realwordhaskell STM](http://book.realworldhaskell.org/read/software-transactional-memory.html)
* Python: пакет Durus
* Java/Scala: фреймворк Akka
[Akka STM](http://doc.akka.io/docs/akka/2.1.4/java/stm.html)
* ScalaSTM, CCSTM
[scala-stm](http://nbronson.github.io/scala-stm/)

Поддержка на уровне аппаратного обеспечения	
===========================================

* Intel Haswell architecture
    * [haskell-tm](http://www.realworldtech.com/haswell-tm/)
	* [intel-haswll-tsx](http://www.bit-tech.net/news/hardware/2012/02/09/intel-haswell-tsx/)
* IBM Power8
    * [IBM STM](http://arstechnica.com/gadgets/2011/08/ibms-new-transactional-memory-make-or-break-time-for-multithreaded-revolution/)
	* [IBM Power8](http://forums.theregister.co.uk/forum/1/2013/08/27/ibm_power8_server_chip/)

Работы
======

* "An architecture for mostly functional languages" Tom Knight, 1986.
* "Impossibility and Universality Results for Wait-Free Synchronization", Herlihy, 1988.
* "A Methodology for Implementing Highly Concurrent Data Structures", Herlihy, 1990.
* "Wait-Free Synchronization", Herlihy, 1991.
* "A Methodology for Implementing Highly Concurrent Data Objects", Herlihy, 1993.
* "Software Transactional Memory", Nir Shavit and Dan Toutiou, 1997.
* "A Practical Multi-Word Compare-and-Swap Operation", Harris, Fraser, Pratt, 2002.
* "Practical Lock-Free and Wait-Free LL:SC:VL Implementations Using 64-bit CAS", Michael, 2004.
* "The Art of Multiprocessor Programming", Herlihy, Shavit, 2008
* ["Transactional memory: architectural support for lock-free data structures"](http://cs.brown.edu/~mph/HerlihyM93/herlihy93transactional.pdf)
* [TxLinux: using and managing hardware transactional memory in an operating system](http://academic.research.microsoft.com/Paper/4122780.aspx)

Материалы
=========

* [TRANSACT workshop 2012](http://transact2012.cse.lehigh.edu/)
* [TRANSACT workshop 2013](http://transact2013.cse.lehigh.edu/)
* [Works on TM/STM](http://research.cs.wisc.edu/trans-memory/biblio/index.html)
* [MSDN](http://blogs.msdn.com/b/devdev/archive/2005/10/20/483247.aspx)
* [SO answer](http://stackoverflow.com/questions/11255640/what-is-transactional-memory)
