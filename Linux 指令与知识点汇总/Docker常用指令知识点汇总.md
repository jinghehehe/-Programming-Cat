# Docker常用指令知识点汇总
## 软件开发最大的麻烦事之一，就是环境配置。为了保证在不同机器上可以顺利运行应用，将软件放在虚拟机和容器是最常用的方法。
- 虚拟机虽然可以解决环境的问题，但其由于资源占用多，冗余步骤多，启动慢等特点不再适用。
- 由于虚拟机存在这些缺点，linux发展了另一种虚拟技术：容器。相应地，其具备启动快，资源占用少，体积小等特点。
- Docker属于linux容器的一种封装，提供简单易用的容器使用接口。它是目前最流行的 Linux 容器解决方案。
- Docker的用途
1. 提供一次性的环境。比如，本地测试他人的软件、持续集成的时候提供单元测试和构建的环境。

2. 提供弹性的云服务。因为 Docker 容器可以随开随关，很适合动态扩容和缩容。

3. 组建微服务架构。通过多个容器，一台机器可以跑多个服务，因此在本机就可以模拟出微服务架构。


## Docker常用指令汇总
- 从网络上拉取基础镜像
```language
docker pull xxxxx    
```

- 查看已有镜像
```language
docker images   
```

-创建容器并使用gpu
```language
docker run -itd --gpus all --name CONTAINER_NAME IMAGE_NAME:TAG  /bin/bash
```

- 启动容器
```language
docker start CONTAINER_NAME
```

-连接至容器
```language
docker attach CONTAINER_NAME    
```

***
- 进入容器后安装所需要的环境pip，conda虚拟环境直接移植（未成功，理论可行）
- 将项目拷贝至容器内
```language
docker cp PROJECT_NAME CONTAINER_NAME:/xxxx(容器内的路径)
```
***
- 将运行的容器保存为镜像
```language
docker commit CONTAINER_NAME IMAGE_NAME   
```

- 将镜像压缩为压缩包
```language
docker save IMAGE_NAME -o ZIP_NAME.tar   
```

- 镜像载入
```language
docker load -i xxx.tar   
```

***
其他指令：
- 删除镜像
```language
docker rmi IMAGEID/REPOSITORY:TAG   
```

- 删除容器
```language
docker rm CONTAINER_NAME   
```

- 查看已有容器（-a表示正在运行的）
```language
docker ps (-a)   
```

- 重命名镜像
```language
docker tag IMAGE REPOSITOY:TAG   
```

- 重命名容器名
```language
docker old_CONTAINER_NAME new_CONTAINER_NAME   
```

- 打包压缩镜像
```language
docker save image_name -o xx.tar 
```

- 容器保存镜像
```language
docker commit container_name image_name 
```

***
### **喜欢Programming-Cat的话，请Star吧**



