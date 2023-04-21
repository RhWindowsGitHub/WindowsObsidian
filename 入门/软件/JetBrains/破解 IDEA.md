

```ad-summary
title:概述
记录 IDEA 的破解方法（2022.+ 版本和 2021.+ 版本）
```

# 破解 IDEA

```ad-tip
title:INFO
作者：Cola

时间：2023-04-16 19:09 
```

```ad-todo
title:Features： 🐔
 - [x] 2022.+ 版本
 - [x] 2021.+ 版本
```

## 2022.+ 版本

1. 下载拦截插件

> [gitee 仓库](https://gitee.com/ja-netfilter/ja-netfilter/releases/tag/2022.2.0) 进入网站后下载相关的包

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416191905.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416191913.png)



2. 配置相应的服务器文件

> [Key](https://3.jetbra.in/) 进入网址后等待扫描完成后点击用时较短的服务器进入

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416191940.png)

```ad-important
注意：需保证所对应的 `Key` 可以被复制
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192025.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192041.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192049.png)

3. 将由 `Key` 网站下载的文件 `config`目录中的 文件替换到由 `gitee` 下载的文件 `config`目录中

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192115.png)

> 替换到

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192127.png)

> 将生成的最终文件存放于不经常使用的目录下（此文件即为拦截所必须的 jar）

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192141.png)

```ad-important
title: 打包好的文件
也可以直接使用打包好的拦截插件 [[IDEA ja-netfilter]]
```


5. 设置 IDEA 的配置文件

> 使用 ToolBOX 快速打开配置文件所在位置

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416193703.png)

> 填入 JDK

```xml
--add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED
--add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED

```
 
  >填入拦截文件所在的绝对路径：`-javaagent:绝对路径` 需使用反斜杠 `\`
  
```xml
  -javaagent:C:\Users\q1203\Documents\ja-netfilter\ja-netfilter.jar
```

>输入先前复制好的 `key`，启动软件后输入即可

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416192321.png)

## 2021.+ 版本

1. 下载对应的拦截包

[点击此处下载](https://raw.githubusercontent.com/1203952894/cloudimg/main/ja-netfilter-all.7z)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416193135.png)

- 设置 IDEA 的配置文件

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416193314.png)

- 输入 `Key`

> Key [[IDEA 2021 ja-netfilter]]

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230416193605.png)