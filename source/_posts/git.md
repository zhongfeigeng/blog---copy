---
title: git
---

https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00150154460073692d151e784de4d718c67ce836f72c7c4000
Linus在1991年创建了开源的Linux
CVS、SVN这些免费的版本控制系统吗？因为Linus坚定地反对CVS和SVN，这些集中式的版本控制系统不但速度慢，而且必须联网才能使用。有一些商用的版本控制系统，虽然比CVS、SVN好用，但那是付费的，和Linux的开源精神不符。
<!--more-->
2002年，Linux系统已经发展了十年了，代码库之大让Linus很难继续通过手工方式管理了，社区的弟兄们也对这种方式表达了强烈不满，于是Linus选择了一个商业的版本控制系统BitKeeper，BitKeeper的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统。
安定团结的大好局面在2005年就被打破了，原因是Linux社区牛人聚集，不免沾染了一些梁山好汉的江湖习气。开发Samba的Andrew试图破解BitKeeper的协议（这么干的其实也不只他一个），被BitMover公司发现了（监控工作做得不错！），于是BitMover公司怒了，要收回Linux社区的免费使用权。Linus可以向BitMover公司道个歉，保证以后严格管教弟兄们，嗯，这是不可能的。实际情况是这样的：
Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！一个月之内，Linux系统的源码已经由Git管理了！牛是怎么定义的呢？大家可以体会一下。Git迅速成为最流行的分布式版本控制系统，尤其是2008年，GitHub网站上线了，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby等等。
ls --ah
Git comes with a tool called git config that lets you get and set configuration variables that control all aspects of how Git looks and operates. These variables can be stored in three different places:
	1. /etc/gitconfig file: Contains values applied to every user on the system and all their repositories. If you pass the option --system to git config, it reads and writes from this file specifically. (Because this is a system configuration file, you would need administrative or superuser privilege to make changes to it.)
	2. ~/.gitconfig or ~/.config/git/config file: Values specific personally to you, the user. You can make Git read and write to this file specifically by passing the --global option, and this affects all of the repositories you work with on your system.
	3. config file in the Git directory (that is, .git/config) of whatever repository you’re currently using: Specific to that single repository. You can force Git to read from and write to this file with the --local option, but that is in fact the default. (Unsurprisingly, you need to be located somewhere in a Git repository for this option to work properly.)
If you want to check your configuration settings, you can use the git config --list command to list all the settings Git can find at that point:
$ git config --list
user.name=John Doe
user.email=johndoe@example.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
 
Git 里面的 origin 到底代表啥意思?
 
作者：田雅文
链接：https://www.zhihu.com/question/27712995/answer/39946123
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
你的代码库(repository)可以存放在你的电脑里，同时你也可以把代码库托管到Github的服务器上。在默认情况下，origin指向的就是你本地的代码库托管在Github上的版本。我们假设你首先在github上创建了一个Repository，叫做repository，假设你的Github ID是user1,这个时候指向你的代码库的链接是
https://github.com/user1/repository
如果你在terminal里输入
git clone https://github.com/user1/repository
那么git就会在本地拷贝一份托管在github上的代码库这个时候你cd到repository然后输入
git remote -v
你会看到控制台输出
origin https://github.com/user1/repository.git (fetch)
origin https://github.com/user1/repository.git (push)
也就是说git为你默认创建了一个指向远端代码库的origin（因为你是从这个地址clone下来的）再假设现在有一个用户user2 fork了你个repository，那么他的代码库链接就是这个样子
https://github.com/user2/repository
如果他也照着这个clone一把，然后在他的控制台里输入git remote -v
他会看的的就是
origin https://github.com/user2/repository.git (fetch)
origin https://github.com/user2/repository.git (push)
可以看的origin指向的位置是user2的的远程代码库这个时候，如果user2想加一个远程指向你的代码库，他可以在控制台输入
git remote add upstream https://github.com/user1/repository.git
然后再输入一遍 git remote -v输出结果就会变为
origin https://github.com/user2/repository.git (fetch)
origin https://github.com/user2/repository.git (push)
upstream https://github.com/user1/repository.git (push)
upstream https://github.com/user1/repository.git (push)
增加了指向user1代码库的upstream，也就是之前对指向位置的命名。总结来讲，顾名思义，origin就是一个名字，它是在你clone一个托管在Github上代码库时，git为你默认创建的指向这个远程代码库的标签， @陈肖恩的答案并不准确，origin指向的是repository，master只是这个repository中默认创建的第一个branch。当你git push的时候因为origin和master都是默认创建的，所以可以这样省略，但是这个是bad practice，因为当你换一个branch再git push的时候，有时候就纠结了
