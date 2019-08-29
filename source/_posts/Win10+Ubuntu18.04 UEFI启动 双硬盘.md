---
title: ubuntu18.04安装ibus拼音输入
---

安装iBus框架
运行命令sudo apt-get install ibus ibus-clutter ibus-gtk ibus-gtk3 ibus-qt4
启动iBus框架
im-config -s ibus
im-switch -s 
<!--more-->
ibus（官方文档上讲的用这个，但是实际，im-switch 不存在，用上面那个就好）
安装ibus拼音输入引擎
运行命令sudo apt-get install ibus-pinyin
启用ibus-pinyin
命令行输入ibus-setup
ibus输入法安装
在中文语言包安装完成后，就需要安装ibus输入法了，需要在Terminal中输入：
sudo apt-get install ibus ibus-clutter ibus-gtk ibus-gtk3 ibus-qt4
1
来安装ibus框架。用
im-config -s ibus
1
切换到ibus框架。再安装拼音引擎：
sudo apt-get install ibus-pinyin
1
再调出ibus Preference来添加该拼音输入法：
sudo ibus-setup
1
在弹出对话框中 （点击add搜索chinese,点击选择pinyin,若找不到。尝试先
重启！重启！重启！
一下，再进去设置，就有了）
在系统设置的区域与语言中添加iBus的智能拼音输入法如下图








