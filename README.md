
2020-06-16,16点29





docker 链接 pycharm

https://www.cnblogs.com/wholj/p/10676917.html



docker run -ti --user root  -p 10022:22      437294e184df  /bin/bash
进入后启动ssh即可.            /usr/sbin/sshd -D &
然后链接127.0.0.1  端口10022

用pycharm 的ssh 链接 即可.


容器杀死后如何重新连接:
	只需要运行上面docker run 然后启动ssh. pycharm就会自动连接到上次的位置.
	pycharm只记忆ip和端口对于哪个容器的服务他不管.

使用这个方法的优势和劣势:
	1.自己电脑性能不行: docker只是用的cpu, 没法用gpu训练. 当然也有nvidia-docker的解决方案
	2.比较吃内存.docker等于虚拟出来一个操作系统.注意设置好docker的内存空间.我设置2.5G
	3.文件拷贝速度很快.都等于本机拷贝.比网络传输快多了.
	4.所以适合代码调试.毕竟pytorch的cuda版本和cpu版本没有区别.
	
	
	
	
