# Git-Study
1. 分布式版本控制系统
  优点：使用简单
  缺点：中央服务器出现故障，所有人无法工作
  
2. 集中式版本控制系统
  优点：每台服务器都有完整的项目

3. 安装
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

—————————————————————————————————

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

—————————————————————————————————

git init my-repo 直接创建名为 my-repo 的仓库
结果：Initialized empty Git repository in C:/Users/Owner/learn-git/.git/my-repo/.git/

方式二：
创建远程仓库
git clone

git clone https://github.com/shadowandsilver/Git-Study.git


4. 分区
工作区 Working Directory
暂存区 Staging Area/Index
本地仓库 Local Repository

git add 工作区的数据提交到暂存区 （数据积累到一定成都后，才会提交（Linux生产者-消费者模式））
git commit 暂存区的数据提交到本地仓库

四种状态
未跟踪 Untrack
未修改 Unmodified
已修改 Modified
已暂存 Staged

5. 添加和提交文件
git status 查看仓库的状态
git add 添加到暂存区
git commit 提交

—————————————————————————————————

git status
结果：
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

—————————————————————————————————

$ git status
结果
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file1.txt （未在仓库中的文件时红色）

nothing added to commit but untracked files present (use "git add" to track)

—————————————————————————————————

git add file1.txt 添加文件 （提交到暂存区中）

$ git status
结果
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   file1.txt （在仓后中后，变为绿色）

—————————————————————————————————

需要使用 -m 指定提交的信息
git commit -m 

exa: git commit -m "第一次提交"

结果：
[master (root-commit) a8152fa] 第一次提交
 1 file changed, 1 insertion(+)
 create mode 100644 file1.txt

git add *.txt 添加所有文件至暂存区中

git log 查看提交记录

 6. git reset 回退版本
git rest --soft 回退到某一版本，保留工作区所有修改的内容
git rest --hard 回退到某一版本，并且删除工作区和暂存区中的所有内容
git rest --mixed 回退到某一版本，保留工作区的内容，丢弃暂存区中的内容

实例：
git rest --soft 版本ID

exa: git rest --soft -0500

7. git diff 查看版本和文件的差异
git diff
查看工作区和暂存区的内容是否相同

 git diff HEAD
 产看工作区和版本库之间的差异

git diff --cache
git diff HEAD 比较暂存区和工作区

git diff 5af90b8 b270efb （版本号1 版本号2）
比较两个版本的差异

git diff 5af90b8 HEAD
某个版本与HEAD进行比较

git diff HEAD~ HEAD
上个版本与当前版本进行比较

git diff HEAD~2 HEAD
与上两个版本进行比较

git diff HEAD`2 HEAD file3.txxt
只比较两个版本中的file3文件的差异






















