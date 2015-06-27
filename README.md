# iNexus
iNexus is a high available key-value store, which can be used to coordinate large scale services. (based on Raft protocol)


iNexus (简称ins) 是一个基于Raft协议实现的高可用的分布式Key-Value数据库，支持数据变更通知（Watch）和分布式锁，可用于大型分布式系统的协调工作

[![Build Status](https://travis-ci.org/fxsjy/ins.svg?branch=master)](https://travis-ci.org/fxsjy/ins)

# 使用说明
https://github.com/fxsjy/ins/wiki

# build for Baiduer
* comake2 -UB
* comake2
* make

# 通用的编译方式
* read [.travis.yml](https://github.com/fxsjy/ins/blob/master/.travis.yml) and install the depends libs
* make && make install

# 快速体验（只需要一台机器，通过多个进程模拟分布式）

	cd sandbox
	./start_all.sh
	./ins_shell.sh
		
	galaxy ins> help
	  show [ show cluster ]
	  put (key) (value) [ update the data ] 
	  get (key) [read the data by key ]
	  delete (key) [remove the data by key]
	  scan (start-key) (end-key) [scan from start-key to end-key(excluded)]
	  watch (key) [event will be triggered once value changed or deleted]
	  lock (key) [lock on specific key]
	  enter quit to exit shell
  ![Screenshot](https://raw.githubusercontent.com/fxsjy/thirdparty/master/ins_screen_shot.png)
  
# 读写性能 (multiple clients， 5 cluster-nodes in LAN)
* 53200 read per second
* 9100 write per second

# use the SDK (client library)
* include [ins_sdk.h](https://github.com/fxsjy/ins/blob/master/sdk/ins_sdk.h) , link the static library libins_sdk.a
* usage example: https://github.com/fxsjy/ins/blob/master/sdk/sample.cc
