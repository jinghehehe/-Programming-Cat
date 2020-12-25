# Linux 脚本常用知识点汇总
***
**脚本操作主要包括运行脚本，脚本权限设置，windows转linux脚本格式不兼容问题。**
***
## 
```language
- shell脚本从windows转到linux易出现权限和文件格式转换问题
其中文件转换
```language
vi xxx.sh
set ff=unix
:wq
```
```
