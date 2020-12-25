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

### 执行脚本
```language
#查看显存
nvidia-smi
```