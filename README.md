subDomainsBrute 1.0.6
======

A simple and fast sub domain brute tool for pentesters. It can rearch as fast as 1000 DNS queries per second.

这个脚本的主要目标是发现其他工具无法探测到的域名, 如Google，aizhan，fofa。高频扫描每秒DNS请求数可超过1000次。

## Change Log (2017-6-3) ##
* 增加CNAME扫描，扫描时间将增加
* Bug fix: normal_lines remove deep copy issus, thanks @BlueIce


## Change Log
* 使用协程替代了多线程
* 使用了优化级队列，来减小队列的长度
* 增加了占位符{next_sub}


## Dependencies ##
> pip install dnspython gevent


## Usage ##

	Usage: subDomainsBrute.py [options] target.com
	
	Options:
	  --version             show program's version number and exit
	  -h, --help            show this help message and exit
	  -f FILE               A file contains new line delimited subs, default is
	                        subnames.txt.
	  --full                Full scan, NAMES FILE subnames_full.txt will be used
	                        to brute
	  -i, --ignore-intranet
	                        Ignore domains pointed to private IPs
	  -t THREADS, --threads=THREADS
	                        Num of scan threads, 200 by default
	  -o OUTPUT, --output=OUTPUT
	                        Output file name. default is {target}.txt