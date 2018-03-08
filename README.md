## aria2c-macOS-128-threads
![1626579-d8617296feef88b1](https://ws3.sinaimg.cn/large/006tNc79gy1fp58oqa50nj31kw0m3gos.jpg)

### Features

- 支持百度云多线程 (128线程) 下载 （_需要浏览器插件支持_）
- 支持网盘的 aria2 导出（_需要浏览器插件支持_）

### Manual

#### Aria2

- 使用 homebrew 安装 aria2 
  - 将 release 中 `aria2c ` 进程文件替换 _/usr/local/celluar/aria2/版本号/aria2c_  
  - 将 `aria2c.conf` 配置放置于 /.aria2/ 目录下, 若没有该文件夹需要在 `终端` 新建该隐藏文件夹  _sudo mkdir /.aria2/_ 
  - 第一次使用的时候会出现 `aria2.session` 文件不存在的错误, 手动创建一个空文件即可.  请在终端敲击 `sudo touch /etc/aria2/aria2.session` 命令即可
  - 你可以使用 ` ~/Library/LaunchAgents` 设置 ` aria2c` 开机后台启动, 详细参见 [Mac 下开机启动 Aria2](http://blog.zhaochunqi.com/2015/12/13/aria2-auto-start/)
- 使用 Aria2GUI 
  - 更改二进制进程名为aria2gui, 替换`显示包文件` - `Contents` - `MacOS ` - `aria2gui` 


#### Chrome

##### BaiduExporter

- 配置插件
  - 从 [BaiduExporter 主页](https://github.com/acgotaku/BaiduExporter) clone 一份到 `~/ ` ，在 Chrome **开发者模式** 下加载插件，图文并茂教程请参见 [Aria2 - macOS 百度云下载神器 (11.29 更新)](https://www.jianshu.com/p/6df3663fb472)
  - `导出下载` - `设置` - `RPC 地址` 设置为（百度云默认是 16 线程）
    - http://localhost:6800/jsonrpc#max-connection-per-server=128&split=128

