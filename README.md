# chrome-dns-clear

   这是一个清理Chrome DNS 缓存组件 基于[chrome-remote-interface](https://github.com/cyrus-and/chrome-remote-interface)开发。

## 使用

```
   npm install chrome-dns-clear
```

## 先决条件

google浏览器必须配置如下启动参数：

1. --enable-benchmarking : 启用基准测试扩展
2. --enable-net-benchmarking : 启用网络基准测试扩展
3. --remote-debugging-port=9222 : 开启远程调试

```
   google-chrome --enable-benchmarking --enable-net-benchmarking --remote-debugging-port=9222
```

### 配置window

1. 快捷方式

  ![快捷方式](https://user-images.githubusercontent.com/22534950/46649062-2fc3e600-cbca-11e8-8ef8-e87aa5e582b5.jpg)

  > 注意： 任务栏中的快捷方式必须重新锁定，才能生效

2. 注册表 (全局配置)

   路径：`HKEY_LOCAL_MACHINE\SOFTWARE\Classes\ChromeHTML\shell\open\command`

   修改为： `"/YOUR_CHROMEPATH/chrome.exe" --enable-benchmarking --enable-net-benchmarking --remote-debugging-port=9222 -- "%1"`

  ![注册表](https://user-images.githubusercontent.com/22534950/46649063-305c7c80-cbca-11e8-83f4-f4bbf5cacf35.jpg)

### 配置macOS

1. 切换Google安装目录

   ```bash
   cd "/Applications/Google Chrome.app/Contents/MacOS/"
   ```
   
2. 重命名的启动脚本

   ```bash
   sudo mv "Google Chrome" Google.real
   ```
   
3. 编辑启动脚本

   ```bash
   vim "Google Chrome"
   ```
   
4. 键入启动参数

   ```bash
      #!/bin/bash
      cd "/Applications/Google Chrome.app/Contents/MacOS"
      "/Applications/Google Chrome.app/Contents/MacOS/Google.real" --enable-benchmarking --enable-net-benchmarking --remote-debugging-port=9222
   ```
   ![键入启动参数](https://user-images.githubusercontent.com/22534950/46655908-6821ef00-cbdf-11e8-9d38-006823ce9cde.jpg)
   
5. `shift` + `q` 退回命令模式 `x` 保存并退出

6. 添加执行权限

   ```bash
   sudo chmod u+x "Google Chrome"
   ```
   
   ![完整效果](https://user-images.githubusercontent.com/22534950/46655909-6821ef00-cbdf-11e8-811e-2d8eaa57b46c.jpg)
