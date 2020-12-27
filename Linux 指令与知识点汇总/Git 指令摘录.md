# Git 指令摘录
***
**Git是常用的版本控制工具，本文将摘录一些常用指令。**
***
### Git 版本初始化
```language
克隆远程库
git clone xxx.git localpath
//输入账号密码
```
```language
//在本地创建目录初始化，git会对该目录下的文件进行版本控制。
git init 
//利用'git remote add'命令来增加一个远程服务器端
git remote add origin xxx.git
git remote add [name] [url]
```

### Git 推送分支与下拉分支
```language
//推送分支
git push <远程主机名> <本地分支名>:<远程分支名>
git push origin master
//下拉分支
git pull <远程主机> <远程分支>:<本地分支>
git pull origin master:my_test
```

