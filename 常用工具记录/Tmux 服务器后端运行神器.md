# Tmux 服务器后端运行神器
***
**在终端运行程序时，终端断掉，程序也会自动断掉，nohup有时也存在问题。**
***
### tmux安装
```language
# Ubuntu 或 Debian
sudo apt-get install tmux

# CentOS 或 Fedora
sudo yum install tmux
```
### tmux新建窗口
```language
# tmux新建窗口
tmux new -s <session-name>
```

### tmux连接和分离窗口
```language
# tmux连接窗口
tmux attach -t <session-name>
# tmux分离窗口
tmux detach
```

### tmux 显示会话
```language
tmux ls
```



