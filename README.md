# aria128-128-macos
![1626579-d8617296feef88b1](https://ws3.sinaimg.cn/large/006tNc79gy1fp58oqa50nj31kw0m3gos.jpg)
### Features
- 主程序已突破线程限制 （支持 128 线程）
- 支持一键开启三个监听端口 （Port 6800, 6801, 6802）
- 自动设置开机启动 (后台运行)
### Manual
#### 双击 Setup 脚本
- 复制百度云导出下载
- 设置开机启动
- 运行 aria2c 监听端口分别为 6800, 6801, 6802
- 跳转多端口 WebGUI Aria2NG
#### 百度云导出下载设置
- Setup 脚本默认将 [Baiduexporter](https://github.com/acgotaku/BaiduExporter) 插件放置于 `/Users/shared/aria2/` 
- Chrome 访问 `chrome://extensions/`, 开启开发着模式, 加载 `/Users/shared/aria2/` 下的 Chrome 文件夹
- 访问 [百度网盘](pan.baidu.com) 正常情况下你应该你能看到 `导出下载` 按钮
- 导出下载 - 设置 - 添加 RPC
  - http://localhost:6800/jsonrpc#max-connection-per-server=128&split=128
  - http://localhost:6801/jsonrpc#max-connection-per-server=128&split=128
  - http://localhost:6802/jsonrpc#max-connection-per-server=128&split=128
- (10.22)目前在未登录百度云账号状态下，导出下载无法成功导出
