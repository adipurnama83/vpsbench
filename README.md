# vpsbench

A script to run simple and comprehensive benchmarks on CPU and IO performance.


Tested on:

* Debian 6.0.6
* Ubuntu 12.04 LTS


## Usage

	Usage: vpsbench [OPTION...]

	-q Quick benchmark
	-d Bench downloads
	-f Create 100M bigfile
	-x Remove temporary files
	-u Bench unixbench


Example pre-requisites

	apt-get update && apt-get install build-essential time pigz


Example


	$ bash <(wget --no-check-certificate -O - https://raw.github.com/CoreVPS/vpsbench/master/vpsbench)

	CPU model:  Intel(R) Core(TM) i7-3770 CPU @ 3.40GHz
	Number of cores: 4
	CPU frequency:  3417.879 MHz
	Total amount of RAM: 3265 MB
	Total amount of swap: 1021 MB
	System uptime:   8:41,
	I/O speed:  427 MB/s
	Bzip 25MB: 4.66s
	Download 100MB file: 1.64MB/s


## License

Licensed under [The MIT License](LICENSE)
