# 文件传输scp知识点总结
***
**将数据上传到服务器，或者服务器之间传输数据时，常用指令汇总**
***
##
### scp传输文件和目录指令（有一个更强大的传输工具rsync，可以查询使用）
- 从服务器下载整个目录（文件只需要不加参数-r）（-v 输出具体传输信息）
```language
scp -r username@servername:remote_dir/ /tmp/local_dir 
```
- 上传目录到服务器
```language
scp  -r /tmp/local_dir username@servername:remote_dir
```
- 以上指令限于linux->linux,windows可采用WinScP，termius等SFTP客户端进行拉取文件，大文件需要在服务器上安装工具来传送。
- lrzsz（Linux服务器和window互传文件工具）
安装 sudo apt-get install lrzsz，传输文件大小限制为4G
- 将选定的文件发送（send）到本地机器
```language
sz file
```
- 从本地选择文件上传到服务器(receive)
```language
rz
```
- 在两个远程主机之间复制文件
```language
scp user1@remotehost1:/some/remote/dir/foobar.txt user2@remotehost2:/some/remote/dir/
```

***
### **喜欢Programming-Cat的话，请Star吧**