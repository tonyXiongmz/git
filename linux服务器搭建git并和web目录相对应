1、yum安装git
yum install -y git

2、建立git仓库目录
mkdir -p /home/git

3、配置一个git用户及用户组
groupadd git
useradd git -d /home/git -g git
passwd  密码

4、建立git仓库
git init --bare xxx.git


5、在本地客户端连接远程仓库
git clone git@ip地址:/home/git/xxx.git

6、建立服务器web目录
mkdir -d /home/www可以是任意位置
并绑定git用户组
chown git:git /home/www
查看文件读写权限，如果不足进行补齐

7、关联仓库到web目录
cd /home/git/xxx.git/hooks
vim post-receive
写入以下内容
#!/bin/bash
git --work-tree=/home/www checkout -f

8、将post-receive绑定到git用户组
chown git:git post-receive
并设置权限
chmod +x post-receive

