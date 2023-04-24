

```ad-summary
title:概述
记录在 IDEA 配置 Maven
```

# Maven 的配置

```ad-tip
title:INFO
作者：Cola

时间：2023-04-21 19:53 
```

```ad-todo
title:Features： 🐔
 - [x] 
 - [x] 
 - [x] 
```

### 一、 配置本地仓库

在 `apache-maven-3.9.1\conf` 目录下的 `settings.xml` 的：

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422031242.png)


插入

```xml
<localRepository>D:\dev_path\Maven\repo</localRepository>
```

其中 `D:\dev_path\Maven\repo` 为需要指定仓库的绝对路径

### 二、 阿里云配置

在 `apache-maven-3.9.1\conf` 目录下的 `settings.xml` 的：

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422030353.png)

插入

```xml
    <mirror>
      <id>maven-default-http-blocker</id>
      <mirrorOf>external:http:*</mirrorOf>
      <name>Pseudo repository to mirror external repositories initially using HTTP.</name>
      <url>http://0.0.0.0/</url>
      <blocked>true</blocked>
    </mirror>
```



### 三、 配置代理

在 `apache-maven-3.9.1\conf` 目录下的 `settings.xml` 的：

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230422030442.png)

插入

```xml
    <proxy>
      <protocol>http</protocol>
      <host>127.0.0.1</host>
      <port>7890</port>
    </proxy>
```

```ad-attention
title:参数含义见注释
e.g.      
- `<host>proxy.host.net</host>` 为 host 主机
- `<port>80</port>` 为 端口
	       
```
