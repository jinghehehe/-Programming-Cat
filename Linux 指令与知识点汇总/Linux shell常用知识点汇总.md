# Linux shell常用知识点汇总
***
**脚本操作主要包括运行脚本，脚本权限设置，windows转linux脚本格式不兼容问题。**
***

### shell脚本从windows转到linux易出现权限和文件格式转换问题
其中文件转换
```language
vi xxx.sh
set ff=unix
:wq
```

### shell脚本首行指令，使用指定解释器执行
- 脚本使用/bin/bash来解释执行
```language
#！/bin/bash 
```

### shell脚本执行方式
- 利用./来执行
```language
./script.sh  
```
- 利用bash(sh)来执行脚本
```language
sh script.sh 或 bash script.sh 
```
- 利用source或. 来执行
```language
source script.sh 
. script.sh 
```
- 上面第三种方式不启用新的shell，在当前shell中执行，设定的局部变量在执行完命令后仍然有效。bash 或 sh 或 shell script 执行时，另起一个子shell，其继承父shell的环境变量，其子shelll的变量执行完后不影响父shell。


### shell脚本中的 exec 命令
- exec 是 bash 的内置命令，shell 的内件命令exec执行命令时，不启用新的shell进程。
- exec是用被执行的命令行替换掉当前的shell进程，且exec命令后的其他命令将不再执行。例如在当前shell中执行 exec ls  表示执行ls这条命令来替换当前的shell ，即为执行完后会退出当前shell。为了避免这个结果的影响，一般将exec命令放到一个shell脚本中，用主脚本调用这个脚本，调用处可以用bash  xx.sh(xx.sh为存放exec命令的脚本)，这样会为xx.sh建立一个子shell去执行，当执行exec后该子脚本进程就被替换成相应的exec的命令。其中有一个例外：当exec命令对文件描述符操作的时候，就不会替换shell，而是操作完成后还会继续执行后面的命令！

[参考链接：](https://www.jianshu.com/p/ca012415cd5f)
- exec与system的区别
1. exec是直接用新的进程去代替原来的程序运行，运行完毕之后不回到原先的程序中去。
2. system是调用shell执行你的命令，system=fork+exec+waitpid,执行完毕之后，回到原先的程序中去。继续执行下面的部分。
3. system 是在单独的进程中执行命令，完了还会回到你的程序中。而exec函数是直接在你的进程中执行新的程序，新的程序会把你的程序覆盖，除非调用出错，否则你再也回不到exec后面的代码，就是说你的程序就变成了exec调用的那个程序了。