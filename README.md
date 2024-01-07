# Git-Study
1.分布式版本控制系统
2.集中式版本控制系统

3.安装
git config --global user.name "abc"
git config --global user.email 123@com

保存账号和邮箱，不用每次登录后，重新输入
git config --global credential.helper store

查看git的配置信息
git config --global --list

4.创建仓库
方式一：git init
方式二： git clone

方式一：
创建仓库，名字是learn-git
mkdir learn-git

进入这个仓库
cd learn-git

初始化仓库
git init
结果：Initialized empty Git repository in C:/Users/Owner/learn-git/.git/

—————————————————————————————————————————————————————————————————————————
注：.git 目录存放了Git仓库的所有数据
需要使用 ls -a 指令
结果：./  ../  .git/

进入.git目录
cd .git
ls -altr
结果：
total 11
drwxr-xr-x 1 Owner 197121   0 Jan  7 00:41 ../
-rw-r--r-- 1 Owner 197121  73 Jan  7 00:41 description
drwxr-xr-x 1 Owner 197121   0 Jan  7 00:41 hooks/
drwxr-xr-x 1 Owner 197121   0 Jan  7 00:41 refs/
drwxr-xr-x 1 Owner 197121   0 Jan  7 00:41 info/
-rw-r--r-- 1 Owner 197121  23 Jan  7 00:41 HEAD
drwxr-xr-x 1 Owner 197121   0 Jan  7 00:41 objects/
-rw-r--r-- 1 Owner 197121 130 Jan  7 00:41 config
drwxr-xr-x 1 Owner 197121   0 Jan  7 00:41 ./

不要随意删除 （\rm -rf .git） 删除后仓库会变成普通文件夹

—————————————————————————————————————————————————————————————————————————
git init my-repo 直接创建名为 my-repo 的仓库
结果：Initialized empty Git repository in C:/Users/Owner/learn-git/.git/my-repo/.git/

方式二：
创建远程仓库
git clone

git clone 








