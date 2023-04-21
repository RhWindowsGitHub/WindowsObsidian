```ad-summary
title：概述
使用 VMware Workstation Pro 安装 CentOS7
```

# 使用 VMware Workstation Pro 安装 CentOS7

```ad-tip
title:INFO
作者: Cola  

时间: 2022/12/17 18:16 PM

描述：使用 VMware Workstation Pro 安装 CentOS7
```

```ad-todo
title:Features： 🐔
 - [ ] VMware Workstation Pro 概述
 - [ ] CentOS 7  安装
 - [ ] 常用服务的安装
```


## 一、VMware Workstation Pro

## 1.1 Vm 概述

> VMWare虚拟机软件是一个“虚拟PC”软件，它使你可以在一台机器上同时运行二个或更多Windows、DOS、LINUX 系统。与“多启动”系统相比，VMWare 采用了完全不同的概念。多启动系统在一个时刻只能运行一个系统，在系统切换时需要重新启动机器.
>
> VMWare虚拟机软件来测试软件、测试安装操作系统（如 Linux）、测试病毒木马等。
>
> VMWare 是真正“同时”运行，多个操作系统在主系统的平台上，就象标准 Windows 应用程序那样切换。而且每个操作系统你都可以进行虚拟的分区、配置而不影响真实硬盘的数据，可以通过网卡将几台虚拟机用网卡连接为一个局域网。

### 1.2 VM 的安装

TOOD

## 二、在 VM 中安装 CentOS 7

### 2.1 `CentOS 7` 的下载

1. 进入 [CentOS 官网](https://www.centos.org/download/) 选择相应版本进行下载，本处采用 `CentOS 7` 64 位

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416083545.png)

2. 随便选择一个所在区域可用的镜像源进行下载

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416083553.png)

3.  选择标准版进行下载

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416083604.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416083613.png)


### 2.2 `CentOS 7` 的配置

1.  打开 `VMware Workstation Pro` 软件，选择 ==创建新的虚拟机==

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084230.png)

2.  选择 ==典型==

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084250.png)

3. 选择 ==稍后安装操作系统==

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084300.png)

4. 选择==相应的操作系统==

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084308.png)

5. 选择 ==安装的路径及虚拟机的名称==

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084318.png)

6. 选择 ==将虚拟磁盘存储为单个文件== 并为其 ==分配空间==

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084328.png)

7. 选择 ==自定义硬件== 并在弹出的对话框配置

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084336.png)


8. 选取下载好的 `ISO` 文件

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084346.png)


### 2.3 `CentOS 7` 的安装

1. 启动创建好的虚拟机，并选择 `install centOS 7`

| 选项                                     | 说明                       |
| ---------------------------------------- | -------------------------- |
| ` Install CentOS 7              `        | 安装CentOS 7               |
| ` Test this media & install CentOS 7   ` | 测试安装文件并安装CentOS 7 |
| ` Troubleshooting     `                  | 修复故障                   |

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084358.png)

2. 选择语言

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084409.png)

3. 选择安装模板

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084416.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084425.png)

4. 选择系统挂载点

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084433.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084450.png)

5. 配置挂载点

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084502.png)


![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084524.png)


![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084514.png)



6. 配置系统根路径，此处不填代表将剩余的空间全部分配

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084542.png)


![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084550.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084601.png)


7. 设置 `root` 用户

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084616.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084626.png)

### 2.4`CentOS 7` 的网络配置

此时我们的虚拟机虽然创建完毕，但无法访问网络因此需要进行相应配置

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084641.png)

#### 2.4.1 自动获取 IP

- 在VMware界面（管理员方式启动）点击“编辑”里面的“虚拟网络编辑器”，然后勾选DHCP服务将IP地址分配给虚拟机，并设置子网IP(默认就好)。
- 点击NAT模式旁边的“NAT设置”，然后修改与子网IP同网段下的网关IP，就是前三位必须相同， 即`192.168.30`要相同，最后一位数不相同即可（其实已经自动设置好了，默认），
- 最后点击“确认”保存设置。

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084701.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084709.png)

---

然后启动虚拟机，进入网络配置文件目录：`cd /etc/sysconfig/network-scripts/`，并且用 ls 命令查看是否有`ifcfg-xxx`名称的配置文件（ ifcfg-lo 除外），如果没有则说明网卡没有被识别，这种只能重装或者换个CentOS的版本。

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084716.png)

1. 编辑 ifcfg-ens33 文件：`vi ifcfg-ens33`。按 i 进入 insert 编辑模式，  ==将BOOTPROTO设为dhcp，将ONBOOT设为yes，== 按下 Esc 进入命令模式输入 :wq 保存并退出。

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084725.png)

 2. 配置完成之后输入：service network restart，重启网卡让网卡设置生效，之后就可以上网了。输入ip addr 检查一下动态分配的 IP

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084736.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084755.png)

3. 最后验证是否可以访问

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416084829.png)

### 2.5 使用`Finalshell` 连接 `CentOS`

TODO