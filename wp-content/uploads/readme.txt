一、
在C盘根目录下建立menu.lst文件，用记事本编辑，将以下内容粘贴进去后，保存退出
color blue/green yellow/red white/magenta white/magenta
timeout 30
default /default

title CentOS
kernel (hd0,0)/isolinux/vmlinuz
initrd (hd0,0)/isolinux/initrd.img

PS：“hd0,0”这里会根据电脑情况有所不同
/"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""/
在命令行下，输入diskpart
list disk
select disk 0
list partition
select partition 8
detail partition
确认c盘所在分区

//________________________________________________________________________________________//
以管理员权限打开命令窗口
bcdedit /create /d "grub" /application bootsector
  提示生成一个{id}
  example:{6ad1ccb4-9b6b-11df-84a0-da2f4806d80e}

  bcdedit /set {6ad1ccb4-9b6b-11df-84a0-da2f4806d80e} device partition=C:
  bcdedit /set {6ad1ccb4-9b6b-11df-84a0-da2f4806d80e} path \grldr.mbr
  bcdedit /displayorder {6ad1ccb4-9b6b-11df-84a0-da2f4806d80e} /addlast


重新启动，此时在引导界面会出现grub选项（注意：在Win系统中，计算机－属性－高级系统设置－高级－启动和故障恢复中要勾选"显示操作系统列表的时间"）选择grub，会出现CentOS,回车开始安装，安装教程网上有，需要注意的是在提directory holding images：__时，要选择CentOS ISO文件所在分区。

三分钟后，你的双系统安装完成