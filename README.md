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

