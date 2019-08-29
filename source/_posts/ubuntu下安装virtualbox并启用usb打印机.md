---
title: ubuntu下安装virtualbox并启用usb打印机
---

打开虚拟系统设置,在“USB设备”标签下,勾选上"启用USB控制器"以及"2.0控制器"增加对USB2.0 的支持。
按说这个时候已经搞定了。可是在USB列表里面却没有任何USB设备。这是为什么呢?谷歌了一下,找到了一篇文章(具体地址已经无法回忆起来了,囧),解释了一下原因。
原来是vbox 所在的用户组比如要包括当前用户才行。
<!--more-->
查看当前用户名:
aliyunzixun@xxx.com:~$ whoami
sharl
查看vbox 所在的组:
aliyunzixun@xxx.com:~$ cat /etc/group | grep vbox
vboxusers:x:125:sharl
将当前用户加入vbox组:
usermod -a -G vboxusers sharl
即可。
此时,重启系统。再次打开虚拟机,果然,USB设备都已经被识别、访问到了。
这些,在“设备”菜单下就可以看到。
添加后,虚拟机系统果然发现了新硬件,按照一般步骤,安装驱动即可正常使用。
