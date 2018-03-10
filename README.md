# aria128c-macOS-128-threads

![1626579-d8617296feef88b1](https://ws3.sinaimg.cn/large/006tNc79gy1fp58oqa50nj31kw0m3gos.jpg)

### Features

- 支持百度云多线程 (128线程) 下载（基于原版 aria2c ）
- 免转存于自己百度网盘 RPC 导出（_需要浏览器插件支持_）

### Manual

#### Aria2

- 配置 aria128c 
  - 将 `aria128c ` 进程文件放置于 _/usr/sbin_ 文件夹下 （如果无法摇拽进该文件夹下, 需要关闭 SIP 验证, [详情请参考](https://www.imore.com/el-capitan-system-integrity-protection-helps-keep-malware-away) ）

  - 将 `aria2c.conf` 配置放置于 /.aria2/ 目录下, 若提示没有该文件夹，则需要在 `终端` 新建该隐藏文件夹  

    > _sudo mkdir /.aria2/_ 

  - 首次使用 aria128c, 需要 

    > sudo mkdir /etc/aria2 && sudo touch /etc/aria2/aria2.session

  - 设置 aria128c 开机启动, 每次调用程序则无需手动敲击命令行启动

    - 打开编辑 `aria128.plist` 
    - 修改 `Working Directory` - `XXXXX` 为你主机的用户名, 应该与绝对地址 /Users/xxxxx 一致的 
    - ![屏幕快照 2018-03-09 下午10.54.43](https://ws2.sinaimg.cn/large/006tNc79gy1fp7pi6eh04j30gs09qmxs.jpg)
    - 如上图, sarkdavidson 为我本机的用户名
    - 修改完成后并保存, 将 `aria128c.plist  `放置于 `~/Library/LaunchAgents` 
- Aria2 第三方封装 Apps 
  - Aria2GUI / Aria2Down,
    - `Aria128c` 更名为 `aria2c`
    - 替换 `显示包文件` - `Contents` - `Resources` - `aria2c` 
    - 修改(`CMD` + `,` )封装程序的 `aria2.conf` 设置参数
      - `max-connection-per-server` = 128
      - `split`=128


#### Chrome

##### BaiduExporter

- 配置插件
  - 从 [BaiduExporter 主页](https://github.com/acgotaku/BaiduExporter) Clone 一份到 `~/ ` ，在 Chrome **开发者模式** 下加载插件，图文并茂教程请参见 [Aria2 - macOS 百度云下载神器 (11.29 更新)](https://www.jianshu.com/p/6df3663fb472)
  - `导出下载` - `设置` - `RPC 地址` 设置为（百度云默认是 16 线程）
    > http://localhost:6800/jsonrpc#max-connection-per-server=128&split=128


