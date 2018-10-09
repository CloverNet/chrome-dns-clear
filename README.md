# chrome-dns-clear

   这是一个清理Chrome DNS 缓存组件 基于[chrome-remote-interface](https://github.com/cyrus-and/chrome-remote-interface)开发。

## 先决条件

   google浏览器必须配置如下启动参数：

   1. --enable-benchmarking : 启用基准测试扩展
   2. --enable-net-benchmarking : 启用网络基准测试扩展
   3. --remote-debugging-port=9222 ： 开启远程调试

   ```
      google-chrome --enable-benchmarking --enable-net-benchmarking --remote-debugging-port=9222
   ```

### 配置window

   1. 快捷方式

     ![快捷方式](https://github.com/CloverNet/chrome-DNS-clear/blob/master/img/window-chrome.jpg?raw=true)

     > 注意： 任务栏中的快捷方式必须重新锁定，才能生效

   2. 注册表 (全局配置)

      路径：HKEY_LOCAL_MACHINE\SOFTWARE\Classes\ChromeHTML\shell\open\command

      修改为： "/YOUR_CHROMEPATH/chrome.exe" *--enable-benchmarking --enable-net-benchmarking --remote-debugging-port=9222* -- "%1"

     ![注册表](https://github.com/CloverNet/chrome-DNS-clear/blob/master/img/window-regedit-chrome.jpg?raw=true)
