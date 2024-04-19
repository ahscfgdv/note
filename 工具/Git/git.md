# GIT

## Git的安装和配置

* git -v

        查看版本

* git config --global user.name "Ljx"

        配置用户名

* git config --global user.email <3384618644@qq.com>

        配置邮箱

* git config --global credential.helper store

        保存用户名和密码

* git config --global --list

        查看配置信息

省略(Local):本地配置,只对本地仓库有效
--global:全局配置,所有仓库生效
--system:系统配置,对所有用户生效

Git的使用方式

* 命令行
* 图形化界面(GUI)
* IDE插件/扩展

## 新建仓库

创建本地文件夹作为仓库
从平台上克隆仓库

* git init

        创建仓库

* git clone <https://github.com/yujiangshui/A-Programmers-Guide-to-English.git>

        克隆仓库

## git的工作区域和文件的状态

![图片](images/屏幕截图%202023-07-13%20132002.png)
![图片](images/屏幕截图%202023-07-13%20132142.png)

### 添加和提交文件

* git status

        查看仓库状态
* git add file

        将文件提交到暂存区

* git add *.txt

        将所有txt文件添加到暂存区
* git add .

        添加所有文件到暂存区

* git rm --cached file

        将文件从暂存区取出

* git commit -m "测试文件"

        将文件从暂存区提交到本地仓库
        -m参数指定提交的信息

* git log

        查看提交记录

* git log --oneline

        查看简化记录

## git reset 回退版本

* git reset --soft

        回退到某个版本保留工作区和暂存区的内容

* git reset --hard

        回退到某个版本不保留工作区和暂存区的内容

* git reset --mixed

        回退到某个版本保留工作区不保留暂存区的内容

## git diff 查看差异

* git diff

        查看工作区和暂存区的不同

* git diff HEAD

        查看工作区和仓库的不同

* git diff --cached

        查看暂存区和仓库的不同

* git diff 164c1d0 8bd2dff

        查看两个版本的不同

* git diff HEAD HEAD~ \<file\>

        查看当前版本和上个版本的不同
        HEAD~ = HEAD^
        HEAD~2 = 之前的两个版本
        <file> 可选参数查看两个版本的指定文件的差异

## git rm 删除文件

* git rm file2.txt

        把文件从工作区和暂存区同时删除

* git rm --cached file2.txt

        把文件从暂存区删除，保留在工作区中

## gitignore 忽略文件

![图片](images/屏幕截图%202023-07-13%20145728.png)

* 配置.gitignore文件

        将忽略的文件名/文件夹或类型写在.gitignore文件中
        对已经追踪的文件不生效

![图片](images/屏幕截图%202023-07-13%20153032.png)
![图片](images/屏幕截图%202023-07-13%20153318.png)

## 远程仓库

获取SSh密钥连接github远程仓库

* git push

将本地仓库推送到远程仓库

* git pull origin main

拉取远程仓库到本地仓库
仓库别名和分支的名称省略的话默认拉取名为origin的main分支
会自动合并到本地仓库

* git fetch

* git remote add origin `git@github.com:ahscfgdv/first-test.git`
将本地仓库上传到远程仓库

## 分支

* git branch
查看所有分支

* git branch dev
创建新的分支dev

* git branch -d dev
删除合并后的分支

* git checkout dev
切换到dev分支

* git switch master
切换到master分支

* git merge dev
合并dev分支到当前分支

## 解决合并冲突

* 手动修改文件

## 回退和rebase

## git常用命令

* git ls-files
查看暂存区内容

## git设置

显示全局配置

* git config --global --list

### git设置代理

socks代理
`git config --global socks.proxy socks5://127.0.0.1:10808`
http代理
`git config --global http.proxy http://127.0.0.1:10809`
https代理
`git config --global https.proxy https://127.0.0.1:10809`


