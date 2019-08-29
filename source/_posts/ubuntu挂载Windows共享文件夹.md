---
title: ubuntu挂载Windows共享文件夹
---

mount -t cifs -o username='youbuntu',password='youbuntu' //192.168.001.105/wysync  /mnt/vBox
# 2.通过修改fstab文件，支持开机自动挂载
# 修改/etc/fstab文件，文件最后加入：
# //192.168.1.100/workspace   /mnt/share cifs  auto,username='echo',password='123456'  0 0
chmod +x ./examples/mnist/bb.sh
