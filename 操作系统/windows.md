# windows

## 环境变量

在配置环境变量时不能将%%开头的变量放在第一行否则不能分行显示

## 输入法

win11，使用微软自带简体中文输入法。切换应用，输入法会自动切换成“英文”输入模式，如何解决？
<https://www.zhihu.com/question/602397490>

## windows防火墙

`netsh advfirewall firewall add rule name="WSL SSH" dir=in action=allow protocol=TCP localport=2200`

这个命令用于在 Windows 高级防火墙中添加一个规则，允许传入的TCP连接到本地端口2200。该规则的名称为"WSL SSH"，意味着它通常用于允许通过SSH（Secure Shell）协议访问Windows Subsystem for Linux（WSL）中运行的服务或应用程序。

解释一下每个参数的作用：
- `netsh`：是一个用于配置网络参数的Windows命令行工具。
- `advfirewall firewall`：这个部分指示了命令的目标，即Windows防火墙的高级配置。
- `add rule`：表示要添加一个新的防火墙规则。
- `name="WSL SSH"`：规则的名称，这里是"WSL SSH"。这个名称在后续的管理和识别规则时会有用。
- `dir=in`：这个规则针对传入的连接，也就是说，它控制着进入系统的连接。
- `action=allow`：这个规则的动作是允许连接通过。
- `protocol=TCP`：这个规则适用于TCP协议的连接。
- `localport=2200`：指定了本地端口2200。这意味着只有目标端口为2200的连接才会被允许通过防火墙。

总之，这个命令的作用是在Windows防火墙中添加一个规则，允许通过TCP连接到本地端口2200，通常用于允许通过SSH访问WSL中的服务。

## windows Powershell

解决“无法加载文件 ***\WindowsPowerShell\profile.ps1，因为在此系统上禁止运行脚本”
<https://zhuanlan.zhihu.com/p/452273123>

## 进程端口管理

```shell
Loading personal and system profiles took 1114ms.
(base) PS C:\Users\ljx> netstat -aon|findstr "8080"
  TCP    0.0.0.0:8080           0.0.0.0:0              LISTENING       10080
  TCP    [::]:8080              [::]:0                 LISTENING       10080
(base) PS C:\Users\ljx> tasklist|findstr "10080"
java.exe                     10080 Console                    1     34,248 K
(base) PS C:\Users\ljx> taskkill /T /F /PID 10080
SUCCESS: The process with PID 16364 (child process of PID 10080) has been terminated.
SUCCESS: The process with PID 10080 (child process of PID 19688) has been terminated.
(base) PS C:\Users\ljx>
```


设置优化<https://www.youtube.com/watch?v=oyWiYyacj0I&t=17s>


```
<VirtualHost 192.168.159.129>
    DocumentRoot "/home/web/test1"
    ServerName test1.com
    <Directory /home/web/test1>
      AllowOverride None
      Require all granted
    </Directory>
</VirtualHost>
```