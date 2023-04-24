

```ad-summary
title:概述
使用 Picgo 搭建图床
```

# 使用 Picgo 搭建图床

```ad-tip
title:INFO
作者：Cola

时间：2023-04-21 20:04 
```

```ad-todo
title:Features： 🐔
 - [x]  ~~使用 腾讯云 COS 作为默认图床~~
 - [ ] 腾讯云 COS 介绍
 - [x] 
```

## 一、 Picgo 概述

>  [Picgo 官网](https://github.com/Molunerfinn/PicGo) **一个用于快速上传图片并获取图片 URL 链接的工具**

### 1.1 搭配腾讯云 COS 搭建图床服务

```ad-attention
title: 注意
此处以腾讯云 COS 为例子，如需了解 COS 请参见：[[COS 对象存储技术#COS 对象存储技术]]
```

1. 获取相关必选参数

> 下图中加 `*` 部分为必选参数

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422024225.png)

2. 获取 `Secretld` 、 `SecretKey` 与 `AppID`

> 进入腾讯云的密钥管理页面[密钥管理页面](https://console.cloud.tencent.com/cam/capi)即可查看相关参数：

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422024604.png)


3. `Bucket` 和 `存储区域的获取`

> 进入腾讯云的[存储桶列表页面](https://console.cloud.tencent.com/cos/bucket)即可查看相关参数：

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422024832.png)

4. 将当前图床设置为默认图床

> 选取对应的图床后，点击右下角按钮将图床设置为默认

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422030041.png)

6. 设置上传快捷键（自选）

```ad-attention
title:设置快捷键（自选）
可通过快捷键实现快速上传至默认图床
```

> 打开 `PicGO` 中设置页面部分的 **设置快捷键** 将 `QUICK_URLOAD` 改为自定义方便快速上传

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422025426.png)

```ad-hint
title: 建议搭配剪切板使用
在 `Win10` 或 `Win11` 上可以使用快捷键 <kbd>win + V</kbd> 的方式打开系统自带的剪切板
```


![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422025746.png)