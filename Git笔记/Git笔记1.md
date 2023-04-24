# ES6 {ignore} 
[toc]

## SSH Key

创建SSH Key

```shell
$ ssh-keygen -t rsa -C "youremail@example.com"
```

测试SSH Key配对成功
```shell
$ ssh -T git@gitee.com
```


## 配置用户信息

```shell
$ git config --global user.name 用户名            
$ git config --global user.email 用户邮箱
```

## 仓库

> 在当前目录新建一个Git代码库，初始化
 
```shell
$ git init
```

> 下载一个项目和它的整个代码历史

```shell
$ git clone [url]
```

## 增加/删除文件

> 添加指定文件到暂存区

```shell
$ git add 文件1 文件2 ...
```


> 添加当前目录的所有文件到暂存区

```shell
$ git add .
```

## 代码提交

> 提交暂存区到仓库区

```shell
$ git commit -m 文件
```

## 查看信息

> 显示有变更的文件

```shell
$ git status
```

> 显示当前分支的版本历史

```shell
$ git log
```

> 显示暂存区和工作区的差异

```shell
$ git diff
```

> 显示当前分支的最近几次提交

```shell
$ git reflog
```

## 分支

> 新建一个分支，但依然停留在当前分支

```shell
$ git branch 要创建的分支名
```

> 新建一个分支，并切换到该分支

```shell
$ git checkout -b [branch]
```

> 切换到指定分支，并更新工作区

```shell
$ git checkout 要切换到的分支
```

> 合并指定分支到当前分支

```shell
$ git merge 被合并的分支名
```

## 撤销

> 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致

```shell
$ git reset --hard [commit]
```

> 新建一个commit，用来撤销指定commit

> 后者的所有变化都将被前者抵消，并且应用到当前分支

```shell
$ git revert [commit]
```

## 远程同步

> 上传本地指定分支到远程仓库
```shell
$ git push [remote] [branch]
```

> 取回远程仓库的变化，并与本地分支合并
```shell
$ git pull [remote] [branch]
```

## 忽略文件配置（.gitignore)

1、配置语法:

> 以斜杠“/”开头表示目录；

> 以星号“*”通配多个字符；

> 以问号“?”通配单个字符

> 以方括号“[]”包含单个字符的匹配列表；

> 以叹号“!”表示不忽略(跟踪)匹配到的文件或目录；

此外，git 对于 .ignore 配置文件是按行从上到下进行规则匹配的，意味着如果前面的规则匹配的范围更大，则后面的规则将不会生效；

2、示例：

　　（1）规则：fd1/*
　　　　  说明：忽略目录 fd1 下的全部内容；注意，不管是根目录下的 /fd1/ 目录，还是某个子目录 /child/fd1/ 目录，都会被忽略；

　　（2）规则：/fd1/*
　　　　  说明：忽略根目录下的 /fd1/ 目录的全部内容；

　　（3）规则：

/*
!.gitignore
!/fw/bin/
!/fw/sf/

说明：忽略全部内容，但是不忽略 .gitignore 文件、根目录下的 /fw/bin/ 和 /fw/sf/ 目录

























