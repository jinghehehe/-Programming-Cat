# profile和bashrc的区别
***
**Linux下通常修改环境需要修改这两个配置文件中的一个，本文简单讲解下这两个配置文件的区别。**
***
## 概念
![](https://github.com/jinghehehe/pictures/blob/main/profile%E5%92%8Cbashrc%E7%9A%84%E5%8C%BA%E5%88%AB.png)
- /etc/profile： 此文件为系统的每个用户设置环境信息,当用户第一次登录时,该文件被执行。是系统全局针对终端环境的设置，它是login时最先被系统加载的，是它调用了/etc/bashrc，以及/etc/profile.d目录下的*.sh文件，如果有一个软件包，系统上只安装一份，供所有开发者使用，建议在/etc/profile.d下创建一个新的xxx.sh，配置环境变量。
- ~/.bashrc:是用户相关的终端（shell）的环境设置，通常打开一个新终端时，默认会load里面的设置，在这里的设置不影响其它人。如果一个服务器多个开发者使用，大家都需要有自己的sdk安装和设置，那么最好就是设置它。
## 总结
**/etc/profile，/etc/bashrc 是系统全局环境变量设定**
**~/.profile，~/.bashrc用户家目录下的私有环境变量设定**
**当登入系统时候获得一个shell进程时，其读取环境设定档有三步:**
1. 首先读入的是全局环境变量设定档/etc/profile，然后根据其内容读取额外的设定的文档，如/etc/profile.d和/etc/inputrc
2. 然后根据不同使用者帐号，去其家目录读取~/.bash_profile，如果这读取不了就读取~/.bash_login，这个也读取不了才会读取~/.profile，这三个文档设定基本上是一样的, 读取有优先关系.
3. 然后在根据用户帐号读取~/.bashrc
4. ~/.profile与~/.bashrc,它们都具有个性化定制功能.
5. ~/.profile可以设定本用户专有的路径，环境变量，等，它只能登入的时候执行一次. ~/.bashrc也是某用户专有设定文档，可以设定路径，命令别名，每次shell script的执行都会使用它一次

[参考资料](https://blog.csdn.net/ZoeYen_/article/details/78560905)
[参考资料](https://www.jianshu.com/p/9d95e5e736da)
***
### **喜欢Programming-Cat的话，请Star吧**

