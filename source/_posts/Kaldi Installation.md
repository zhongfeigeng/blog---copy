---
title: Kaldi Installation
---

openFST make install error, do:
sudo make install
1. git 首先，确认你的系统是否已安装git，可以通过git指令进行查看
如果没有，在命令行模式下输入sudo apt-get install git命令进行安装。

<!--more-->
安装完成后进行git配置，输入指令
git config --global user.name "xxx"
git config --global user.email "你的邮箱地址"
配置完成后，需要创建验证用的公钥，因为git是通过ssh的方式访问资源库的，所以需要在本地创建验证用的文件。使用命令ssh-keygen -C 'you email address@gmail.com' -t rsa（注意ssh与-keygen之间没有空格），会在用户目录~/.ssh/下建立相应的密钥文件。
创建完公钥后，需要上传。使用命令cd ~/.ssh进入~/.ssh文件夹，输入gedit id_rsa.pub打开id_rsa.pub文件，复制其中所有内容。接着访问http://git.oschina.net/profile网页，点击SSH公钥，标题栏可以随意输入，公钥栏把你刚才复制的内容粘贴进去就OK了。
可以使用ssh -T git@git.oschina.net命令来测试连接是否畅通
 
Also, set short names for the most useful git commands you type most often.
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.st status
 
2. get Kaldi
We have now transitioned to GitHub for all future development. You first need to install Git. The most current version of Kaldi, possibly including unfinished and experimental features, can be downloaded by typing into a shell:
git init
git config http.postBuffer 524288000
   git clone https://github.com/kaldi-asr/kaldi.git kaldi --origin upstream
   cd kaldi
If you want to get updates and bug fixes you can go to some checked-out directory, and type
   git pull
If "git pull" prints out a message telling it cannot pull the remote changes because you have changed files local
-------------------------------------------------------------------------------------------------------------------------------------------------
Assuming Git is installed, to get the latest code you can type
    git clone https://github.com/kaldi-asr/kaldi.git kaldi-trunk --origin golden
Then cd to kaldi-trunk. Look at the INSTALL file and follow the instructions (it points you to two subdirectories). Look carefully at the output of the installation scripts, as they try to guide you what to do. Some installation errors are non-fatal, and the installation scripts will tell you so (i.e. there are some things it installs which are nice to have but are not really needed). The "best-case" scenario is that you do:
   cd kaldi-trunk/tools/; make; cd ../src; ./configure; make
and everything will just work; however, if this does not happen there are fallback plans (e.g. you may have to install some package on your machine, or run install_atlas.sh in tools/, or run some steps in tools/INSTALL manually, or provide options to the configure script in src/). If there are problems, there may be some information in The build process (how Kaldi is compiled) that will help you; otherwise, feel free to contact the maintainers (Other Kaldi-related resources (and how to get help)) and we will be happy to help.
Software packages required
The following is a non-exhaustive list of some of the packages you need in order to install Kaldi. The full list is not important since the installation scripts will tell you what you are missing.
	• Git: this is needed to download Kaldi and other software that it depends on.
	• wget is required for the installation of some non-Kaldi components described below
	• The example scripts require standard UNIX utilities such as bash, perl, awk, grep, and make.
It can also be helpful if you have an ATLAS linear-algebra package installed on your system. Most systems already have this (You can also search the packages in linux for installation by simple commands like "yum search atlas" or "apt-cache search libatlas"); the best approach is to ignore this requirement for now and see if you have problems when you install Kaldi.
 
