# vpsbench

A script to run simple and comprehensive benchmarks on CPU and IO performance.

Tested on:

* Debian 6.0.6
* Ubuntu 12.04 LTS
* Ubuntu 14.04 LTS

## Quickstart

```
# Prerequisites on Ubuntu
sudo apt-get update && sudo apt-get install -y build-essential time pigz

# Run extensive benchmark
git clone https://github.com/kofalt/vpsbench.git && cd vpsbench && ./vpsbench -qukx
```

The `-u` option can take nearly an hour; omitting that flag is much quicker.

## Usage

```
Usage: vpsbench [OPTION...]

-q Quick benchmark
-d Bench downloads
-u Bench unixbench
-k Bench kernel compilation
-f Create 100M bigfile
-x Remove temporary files
```

## Example output

Quick results:

```
CPU model:  Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz
Number of cores: 8
CPU frequency:  1600.000 MHz
Total amount of RAM: 15993 MB
Total amount of swap: 0 MB
System uptime:   3:13,
I/O speed:  198 MB/s
Bzip 25MB: 0.27s
Download 100MB file: 6.77MB/s
```

Unixbench results:

```
========================================================================
   BYTE UNIX Benchmarks (Version 5.1.3)

   System: testbed: GNU/Linux
   OS: GNU/Linux -- 3.11.0-12-generic -- #19-Ubuntu SMP Wed Oct 9 16:20:46 UTC 2013
   Machine: x86_64 (x86_64)
   Language: en_US.utf8 (charmap="UTF-8", collate="UTF-8")
   CPU 0: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 1: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 2: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 3: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 4: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 5: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 6: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   CPU 7: Intel(R) Core(TM) i7-3770K CPU @ 3.50GHz (7020.8 bogomips)
          Hyper-Threading, x86-64, MMX, Physical Address Ext, SYSENTER/SYSEXIT, SYSCALL/SYSRET, Intel virtualization
   00:18:47 up  2:15,  3 users,  load average: 0.01, 0.18, 1.20; runlevel 2

------------------------------------------------------------------------
Benchmark Run: Sat Apr 19 2014 00:18:47 - 00:47:06
8 CPUs in system; running 1 parallel copy of tests

Dhrystone 2 using register variables       43430878.2 lps   (10.0 s, 7 samples)
Double-Precision Whetstone                     4100.7 MWIPS (11.6 s, 7 samples)
Execl Throughput                               2220.3 lps   (30.0 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks       1423918.8 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks          381888.2 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks       3429826.2 KBps  (30.0 s, 2 samples)
Pipe Throughput                             2907135.2 lps   (10.0 s, 7 samples)
Pipe-based Context Switching                 102610.9 lps   (10.0 s, 7 samples)
Process Creation                               8473.5 lps   (30.0 s, 2 samples)
Shell Scripts (1 concurrent)                   6228.4 lpm   (60.0 s, 2 samples)
Shell Scripts (8 concurrent)                   4849.2 lpm   (60.0 s, 2 samples)
System Call Overhead                        5165686.0 lps   (10.0 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0   43430878.2   3721.6
Double-Precision Whetstone                       55.0       4100.7    745.6
Execl Throughput                                 43.0       2220.3    516.4
File Copy 1024 bufsize 2000 maxblocks          3960.0    1423918.8   3595.8
File Copy 256 bufsize 500 maxblocks            1655.0     381888.2   2307.5
File Copy 4096 bufsize 8000 maxblocks          5800.0    3429826.2   5913.5
Pipe Throughput                               12440.0    2907135.2   2336.9
Pipe-based Context Switching                   4000.0     102610.9    256.5
Process Creation                                126.0       8473.5    672.5
Shell Scripts (1 concurrent)                     42.4       6228.4   1469.0
Shell Scripts (8 concurrent)                      6.0       4849.2   8081.9
System Call Overhead                          15000.0    5165686.0   3443.8
                                                                   ========
System Benchmarks Index Score                                        1800.2

------------------------------------------------------------------------
Benchmark Run: Sat Apr 19 2014 00:47:06 - 01:15:13
8 CPUs in system; running 8 parallel copies of tests

Dhrystone 2 using register variables      192450518.0 lps   (10.0 s, 7 samples)
Double-Precision Whetstone                    33177.9 MWIPS (9.9 s, 7 samples)
Execl Throughput                              25951.4 lps   (30.0 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks       1241014.4 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks          323635.2 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks       3702982.7 KBps  (30.0 s, 2 samples)
Pipe Throughput                            13207603.6 lps   (10.0 s, 7 samples)
Pipe-based Context Switching                2142193.0 lps   (10.0 s, 7 samples)
Process Creation                              34368.8 lps   (30.0 s, 2 samples)
Shell Scripts (1 concurrent)                  48615.8 lpm   (60.0 s, 2 samples)
Shell Scripts (8 concurrent)                   7193.0 lpm   (60.0 s, 2 samples)
System Call Overhead                       10945286.5 lps   (10.0 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0  192450518.0  16491.0
Double-Precision Whetstone                       55.0      33177.9   6032.4
Execl Throughput                                 43.0      25951.4   6035.2
File Copy 1024 bufsize 2000 maxblocks          3960.0    1241014.4   3133.9
File Copy 256 bufsize 500 maxblocks            1655.0     323635.2   1955.5
File Copy 4096 bufsize 8000 maxblocks          5800.0    3702982.7   6384.5
Pipe Throughput                               12440.0   13207603.6  10617.0
Pipe-based Context Switching                   4000.0    2142193.0   5355.5
Process Creation                                126.0      34368.8   2727.7
Shell Scripts (1 concurrent)                     42.4      48615.8  11466.0
Shell Scripts (8 concurrent)                      6.0       7193.0  11988.4
System Call Overhead                          15000.0   10945286.5   7296.9
                                                                   ========
System Benchmarks Index Score                                        6264.7
```

## License

Licensed under [MIT](LICENSE)
