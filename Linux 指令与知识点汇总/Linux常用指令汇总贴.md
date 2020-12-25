# Linux常用指令汇总贴
***
**汇集Linux系统下所需常用命令，定期更新**
***
## 类别一
### 查看系统文件夹占用大小
```language
#当前目录下文件占用大小
du -h --max-depth=1 .
```

### 查看显存
```language
#查看显存
nvidia-smi
```

### 查看cuda版本和cudnn版本
```language
#查看cuda版本
1. nvcc 安装
nvcc --version 
nvcc -V
2. nvcc 未安装
cat /usr/local/cuda/version.txt

#查看cudnn版本
cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2
```

### 查看显存
```language
#查看显存
nvidia-smi
```

### 环境依赖包生成与安装
```language
#生成requirements.txt文件
pip freeze > requirements.txt
```
```language
#安装requirements.txt依赖
pip install -r requirements.txt
```

### python添加祖父目录文件，使用配置文件方式（sys.path.append有时会出问题）
```language
#类似于windows的环境变量，可以保证import成功。
vi ~/.bashrc
export PYTHONPATH=~/xx/pysot-toolkit/pysot:$PYTHONPATH
source ~/.bashrc
```

### Python多版本切换
- 本人遇到的是操作失误导致anaconda环境中的python版本被切换，进而导致conda启动失败，报错：No module named 'conda'
- 解决方案：指定python版本路径
- 当前终端改变python版本（终端关闭，python版本不变）
适用于调试，或者在一个用户下同时操作两个不同版本的python。
```language
export PATH="/home/xx/2020/miniconda3/bin:$PATH"
```
代码中的路径是你想改变的python版本路径
- 永久改变python版本
1. 修改用户配置环境变量
```language
sudo vi ~/.bash_profile
export PATH="/home/xx/2020/miniconda3/bin:$PATH"
```
2. 使修改后的文件立即生效
```language
source ~/.bash_profile
```
3. （可选）当shell类型为zshell时需要修改vi ~/.zshrc，不然重新开启命令终端时会无效
在最后写入source ~/.bash_profile（未实验）