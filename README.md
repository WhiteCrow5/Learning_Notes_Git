* [1、初始化仓库](#1%E5%88%9D%E5%A7%8B%E5%8C%96%E4%BB%93%E5%BA%93)
* [2、设置签名](#2%E8%AE%BE%E7%BD%AE%E7%AD%BE%E5%90%8D)
* [3、查看状态](#3%E6%9F%A5%E7%9C%8B%E7%8A%B6%E6%80%81)
* [4、工作区到暂存区文件的添加与删除](#4%E5%B7%A5%E4%BD%9C%E5%8C%BA%E5%88%B0%E6%9A%82%E5%AD%98%E5%8C%BA%E6%96%87%E4%BB%B6%E7%9A%84%E6%B7%BB%E5%8A%A0%E4%B8%8E%E5%88%A0%E9%99%A4)
* [5、提交暂存区文件到本地库](#5%E6%8F%90%E4%BA%A4%E6%9A%82%E5%AD%98%E5%8C%BA%E6%96%87%E4%BB%B6%E5%88%B0%E6%9C%AC%E5%9C%B0%E5%BA%93)
* [6、查看日志](#6%E6%9F%A5%E7%9C%8B%E6%97%A5%E5%BF%97)
* [7、版本切换](#7%E7%89%88%E6%9C%AC%E5%88%87%E6%8D%A2)
* [8、查看帮助](#8%E6%9F%A5%E7%9C%8B%E5%B8%AE%E5%8A%A9)
* [9、文件比较](#9%E6%96%87%E4%BB%B6%E6%AF%94%E8%BE%83)
* [10、分支管理](#10%E5%88%86%E6%94%AF%E7%AE%A1%E7%90%86)
* [11、远程库](#11%E8%BF%9C%E7%A8%8B%E5%BA%93)
* [12、ssh设置](#12ssh%E8%AE%BE%E7%BD%AE)



#### 1、初始化仓库

```
git init
```



#### 2、设置签名

```
# 项目级别/仓库级别：仅在当前本地库范围内有效	保存在.git/config
git config user.name xxx
git config user.email xxx@xx.com	
# 系统用户级别：登录当前操作系统的用户范围		保存在user/.gitconfig
git config --global user.name xxx
git config --global user.email xxx@xx.com
```



#### 3、查看状态

```
git status
```



#### 4、工作区到暂存区文件的添加与删除

```
# 将未追踪的文件保存到暂存区
git add <file>
# 将暂存区的文件移除
git rm -cached <file>
git reset HEAD <file>
# 取消对暂存区文件的修改
git checkout -- <file>
git restore <file>			#2.23版本新填的 switch 和 restore命令
```



#### 5、提交暂存区文件到本地库

```
git commit <file>
# （推荐）
git commit -m 'message' <file>
```



#### 6、查看日志

```
git log
# 查看前n个日志
git log -n
# 每条日志只显示一行
git log --oneline
git log --pretty=oneline
# 显示出HEAD指针需要移动的步数 （推荐）
git reflog
```



#### 7、版本切换

```
# 移动到指定的版本（推荐）
git reset --hard <hash>
# 使用^ 只能后退
git reset --hard HEAD^ 
git reset --hard HEAD^^
git reset --hard HEAD^^^
...
# 使用~ 指定后退n个版本
git reset --hard HEAD~n

--soft	仅仅在本地库移动HEAD指针	
--mixed	在本地库移动HEAD指针，重置暂存区
--hard	在本地库移动HEAD指针，重置暂存区，重置工作区（推荐）
```



#### 8、查看帮助

```
git help <command>
```



#### 9、文件比较

```
# 将工作区文件和暂存区文件进行比较
git diff <file>
# 将工作区文件和本地库历史记录进行比较
git diff HEAD <file>
```



#### 10、分支管理

```
# 查看分支
git branch -v
# 创建分支
git branch [branchname]
# 切换分支
git checkout [branchname]
# 合并分支
gir merge [branchname]

```



#### 11、远程库

```
# 查看关联的远程库
git remote -v
# 远程添加库
git remote add [远程库地址别名] [address]
# 克隆远程库
git clone [address]
# 推送到远程库
git push [远程库地址别名][远程分支名]
# 拉取远程库
git fetch [远程库地址别名][远程分支名]
git merge [远程库地址别名][远程分支名]
# pull = fetch + merge
git pull [远程库地址别名][远程分支名]
```



#### 12、ssh设置

```
ssh-keygen -t rsa -C [email]
```

