# 视频转rtsp流
***
1. 从http://ffbinaries.com/downloads下载ffserver，网站里有多个版本及多个系统平台，本文用3.4版本ffserver。
2. 解压到自定义目录
```language
~/rtsp$sudo unzip ffserver-3.4-linux-64.zip

~/rtsp$ ls

ffserver  ffserver-3.4-linux-64-1.zip   __MACOSX
```

3. 在ffserver-3.4-linux-64.zip 解压的同级目录，新建ffserver.cfg文件，并写入如下内容：
```language
RTSPPort 5454
BindAddress 0.0.0.0
RTSPBindAddress 0.0.0.0
MaxHTTPConnections 2000
MaxClients 1000
MaxBandwidth 30000
CustomLog -
NoDaemon
#NoDefaults
 
<Stream test.mp4>
File "/home/sdb/work/stream/test.mp4"
Format rtp
</Stream>
```

4. 命令行运行
```language
./ffserver -f server.cfg
```
5. vlc播放
```language
rtsp://ip/test.mp4
```






