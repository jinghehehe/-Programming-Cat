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

### 执行脚本
```language
#查看显存
nvidia-smi
```