# aria2-128-macos
![1626579-d8617296feef88b1](https://i.imgur.com/MagMjGV.gif)
### 特点
- 主程序已突破线程限制 （支持 128 线程）
- 支持一键开启三个监听端口 （Port 6800, 6801, 6802）
- 自动设置开机启动 (后台运行)
- 复制百度云导出下载
### 使用

1. 克隆我的分支 

   > git clone git@github.com:sarkrui/aria2-macOS-128.git

2. 切换当前路径

   >cd aria2-macOS-128

3. 运行脚本

   > chmod +x setup
   >
   > ./setup

#### 百度云导出下载设置
- `Setup 脚本` 默认将 [Baiduexporter](https://github.com/acgotaku/BaiduExporter) 插件放置于 `/Users/shared/aria2/` 

- Chrome 访问 `chrome://extensions/`, 开启`开发着模式`, 加载 `/Users/shared/aria2/` 下的 Chrome 文件夹

- 访问 [百度网盘](pan.baidu.com) 正常情况下你应该你能看到 `导出下载` 按钮

- 导出下载 - 设置 - 添加 RPC 
  - `Port 6800` http://localhost:6800/jsonrpc#max-connection-per-server=128&split=128
  - `Port 6801` http://localhost:6801/jsonrpc#max-connection-per-server=128&split=128
  - `Port 6802` http://localhost:6802/jsonrpc#max-connection-per-server=128&split=128
  - `Google Drive` http://localhost:6803/jsonrpc#max-connection-per-server=128&split=128

  > 如果你是百度 SVIP 用户，split=128 可以保证全速下载，如果是普通用户，超过 16 可能导致账号被限速，可以考虑注册小号来导出下载
  >
  > 如果你是 G Suite 用户，可以直接通过 Google File Steam 将 Google Drive 挂载在 /Volumes/ 下，通过导出下载直接同步至 Google Drive (默认路径 /Volumes/GoogleDrive/My Drive/BaiduStorage)

- 目前 (10.22) 在未登录百度云账号状态下，导出下载无法成功导出

### 鸣谢

* acgotaku, [百度导出下载插件](https://github.com/acgotaku/BaiduExporter)
* Aria2, [aria2 多协议支持的轻量化开源下载工具](https://github.com/aria2/aria2)
* Yadomin, [解除 Aria2 的限制](https://www.jianshu.com/p/f1282f4f704c)
* Zsakvo, [Mac 自编译 Aria2 突破百度云限速并接管系统下载器](https://blog.zsakvo.cc/index.php/archives/26/)
