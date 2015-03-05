---
layout: post
title: "How to quickly install the MockServer"
date: 2015-03-05 16:03:56 +0800
comments: true
categories: 
---
一、环境准备

1.安装homebrew工具（可以用ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"安装

2.安装corkscrew工具（可以用brew install corkscrew安装）

3.安装nodejs（可以用brew install node安装）

如果以上工具都已安装完成，可忽略以上步骤

二、搭建步骤

1.配置本地代理：代理地址：http://10.29.10.12/pac/msp_proxy.pac

2.配置SSH代理：将目录切换到cd ~/.ssh/到ssh文件夹下，将config（切记关掉该文件）文件放置到ssh目录下（可以用命令ssh-keygen 生成/.ssh/文件夹）

3.执行git init：ls后发现默认路径是/Users/twer/.git/（可以通过mkdir，cd命令新建自己的目录，我的目录在MockServer下）

4.在MockServer目录下执行：git remote add origin ssh://git@git02.ae.sda.corp.telstra.com/tx/telstra24x7-mockserver-nodejs.git

5.执行git fetch（在MockServer目录下执行）
执行失败，提示需要RSA key

解决办法：浏览：https://git02.ae.sda.corp.telstra.com/projects/TX
用有权限的Dnumber登陆的，将.ssh文件夹下的ip_psa.pub文件中
得所有的内容拷贝到文本框中，即可添加成功。

这时再次执行git fetch命令成功，且有进度提示

6.执行git checkout master，确保在master的分支上

7.启动服务（可以选一个）
./startDEVMSPServer.sh
./startQAMSPServer.sh
./startSNAPPServer.sh

三、搭建完成后验证

1.访问http://localhost:4000/dashboard 有数据

2.可以ctrl+c或者直接关掉Term，关闭服务器。
