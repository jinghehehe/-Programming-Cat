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

### Git 开源代码其他用户示例
```language
// fork开源项目
git clone <远程Arepository> #克隆你fork出来的分支
 
git remote add <远程Brepository标签> git@github.com:XXXX/ceph.git #添加远程Brepository标签
 
git pull <远程B厂库标签> master:master  #从远程Brepository的master分支拉取最新objects合并到本地master分支

git checkout YYYY #切换到要修改的分支上
 
git branch develop; git checkout develop #在当前分支的基础上创建一个开发分支，并切换到该分支上，你将在该分支上coding
 
coding...... #在工作区coding
 
git add .#将修改保存到索引区
 
git commit -a #将修改提交到本地分区
 
git push origin my_test:my_test #将本地分支my_test提交到远程A repository的my_test分支上

//提交，等待审核。
```

***
### **喜欢Programming-Cat的话，请Star吧**
