## 简介
- Systemd是为系统的启动和管理提供一套完整的解决方案, 同时取代initd。   
- systemctl是Systemd的主命令，用于管理系统。   
- systemd-analyze命令用于查看启动耗时。
- hostnamectl命令用于查看当前主机的信息。
- localectl命令用于查看本地化设置。
- timedatectl命令用于查看当前时区设置。
- loginctl命令用于查看当前登录的用户。

## Unit
Systemd 可以管理所有系统资源。不同的资源统称为 Unit（单位）。
- Service unit：系统服务
- Target unit：多个 Unit 构成的一个组
- Device Unit：硬件设备
- Mount Unit：文件系统的挂载点
- Automount Unit：自动挂载点
- Path Unit：文件或路径
- Scope Unit：不是由 Systemd 启动的外部进程
- Slice Unit：进程组
- Snapshot Unit：Systemd 快照，可以切回某个快照
- Socket Unit：进程间通信的 socket
- Swap Unit：swap 文件
- Timer Unit：定时器

## Unit配置文件
- Systemd 默认从目录/etc/systemd/system/读取配置文件。但是，里面存放的大部分文件都是符号链接，指向目录/usr/lib/systemd/system/，真正的配置文件存放在那个目录。
- 

## 常用命令--systemctl
- `systemctl list-units|list-unit-files` 列出单元|单元文件 
- `systemctl is-enabled 单元名称` 检查某个单元是不是默认启动
- `systemctl status 单元名称` 检查某个单元运行状态, 如过没有单元名称, 则显示所有单元状态
- `systemctl start|stop|restart|reload 单元名称` 启动|停止|重启|重新加载 单元
- `systemctl enable|disable 单元名称` 启用|禁用 随系统启动


## timedatectl命令
- `timedatectl status|set-time|set-timezone|list-timezones` 系统时间状态, 设置时间, 设置时区, 列出全部时区, 如: 把时区设为为中国上海时区`timedatectl set-timezone Asia/Shanghai`


