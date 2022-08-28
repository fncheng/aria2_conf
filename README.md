# aria2使用教程

[ 官网](https://aria2.github.io/)

[下载地址](https://github.com/aria2/aria2/releases/download/release-1.35.0/aria2-1.35.0-win-64bit-build1.zip)

### Aria2 的配置

参考链接： https://zhuanlan.zhihu.com/p/21831960 

配置文件说明： http://aria2c.com/usage.html 

**1**. 打开aria2.conf，复制以下内容到该文件：

```bash
## '#'开头为注释内容, 选项都有相应的注释说明, 根据需要修改 ##
## 被注释的选项填写的是默认值, 建议在需要修改时再取消注释  ##


## 基本设置 ##

# 下载路径(可使用绝对路径或相对路径), 默认: 当前启动位置
dir=D:\Download\
#日志文件位置
log=D:\Aria2\Aria2.log
# 最大同时下载任务数, 运行时可修改, 默认:5
max-concurrent-downloads=5
# 从会话文件中读取下载任务
input-file=D:\Aria2\aria2.session
# 在Aria2退出时保存`错误/未完成`的下载任务到会话文件
save-session=D:\Aria2\aria2.session
# 定时保存会话, 0为退出时才保存, 需1.16.1以上版本, 默认:0
save-session-interval=60
#强制保存
force-save=true
#断点续传
continue=true



## 下载连接相关 ##


# 同一服务器连接数, 添加时可指定, 默认:1
max-connection-per-server=5



# 整体上传速度限制, 运行时可修改, 默认:0
max-overall-upload-limit=50K

# 单个任务上传速度限制, 默认:0
max-upload-limit=20

# Http/FTP options

connect-timeout=120

lowest-speed-limit=10K

max-connection-per-server=10

max-file-not-found=2

min-split-size=1M

split=5

check-certificate=false

http-no-cache=true


## BT/PT下载相关 ##

# 当下载的是一个种子(以.torrent结尾)时, 自动开始BT任务, 默认:true
follow-torrent=true

# BT监听端口, 当端口被屏蔽时使用, 默认:6881-6999
#listen-port=51413

# 单个种子最大连接数, 默认:55
#bt-max-peers=55

# 本地节点查找, PT需要禁用, 默认:false
bt-enable-lpd=true

# 打开DHT功能, PT需要禁用, 默认:true
#enable-dht=false

# 打开IPv6 DHT功能, PT需要禁用
enable-dht6=false

rpc-save-upload-metadata=true
# BT校验相关, 默认:true
#bt-hash-check-seed=true

# 继续之前的BT任务时, 无需再次校验, 默认:false
bt-seed-unverified=true

bt-remove-unselected-file

# 每个种子限速, 对少种的PT很有用, 默认:50K
bt-request-peer-speed-limit=100K

seed-ratio=0.0



## RPC相关设置 ##

# 启用RPC, 默认:false
enable-rpc=true

pause=false

# 允许所有来源, 默认:false
rpc-allow-origin-all=true

# 允许非外部访问, 默认:false
rpc-listen-all=true

rpc-save-upload-metadata=true

# 是否启用 RPC 服务的 SSL/TLS 加密,
# 启用加密后 RPC 服务需要使用 https 或者 wss 协议连接
rpc-secure=false


## 高级设置 ##

daemon=true

# 禁用IPv6, 默认:false
disable-ipv6=true

# 启用磁盘缓存, 0为禁用缓存, 需1.16以上版本, 默认:16M
#disk-cache=32M

#启用MMap
enable-mmap=true

#日志级别
log-level=error

# 全局最大下载速度限制, 运行时可修改, 0表示不限制，默认:0
max-overall-download-limit=0

# 单个任务最大下载速度限制, 默认:0
#max-download-limit=0


# 文件预分配方式, 能有效降低磁盘碎片, 默认:prealloc
# 预分配所需时间: none < falloc ? trunc < prealloc
# falloc和trunc则需要文件系统和内核支持
# NTFS建议使用falloc, EXT3/4建议trunc, MAC 下需要注释此项
file-allocation=falloc 

max-download-result=120

#no-file-allocation-limit=32M

force-sequential=true

parameterized-uri=true
```

**2**. 编辑HideRun.vbs，并复制以下内容，注意修改D:\App\Aria2\为你的aria2安装路径： 

```bash
CreateObject("WScript.Shell").Run "D:\App\Aria2\aria2c.exe --conf-path=aria2.conf",0
```

**3**. 管理Aria 2 下载任务

打开aria2的WebUI，建议使用aria2 for Chrome插件



aria2下载助手被曝含有上传代码(自行决定是否使用)

百度云直链生成，推荐使用哩呵的网盘助手插件，也可以使用[直链下载助手](https://www.baiduyun.wiki/)。
