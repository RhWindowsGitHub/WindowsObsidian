

```ad-summary
title:概述
用于记录 Python 工程组织结构 便于模块化开发
```

# 一、Python 工程组织结构

```ad-tip
title:INFO
作者：Cola

时间：2023-04-17 04:24 
```

```ad-todo
title:Features： 🐔
 - [x] 组织结构概述
 - [x] 模块导入
 - [x] 入口文件
```

## 1.1 组织结构

-   Python 项目的组织结构主要由 **包--模块--类** 这些部分构成。
-   **包：** 可以看成文件夹，可以包含多个模块。如果让普通文件夹变成python的包，在该文件夹下必须包含 **init**.py 文件。`__init__.py` 也是一个特殊的模块，模块名就是包名。
-   **模块：** 可以看成文件，对应 python 中的 .py 文件。一个模块下面也可以包含多个类。模块下面也可以直接写函数。
-   **类：** 类中定义了变量和函数。
-   **函数：** 用于实现特定功能，

## 1.2 模块导入

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417043047.png)


### 1.2.1 import

import **只能引入模块**，不能直接引入变量或函数。

```ad-example
title: 使用 import 导入
示例：在 main.py 文件中导入包 basicPart 中的模块 module1.py 和module2.py。
```

```python
import basicPart.module01  
# 多次调用可以采用重命名方式  
import basicPart.module02 as pm2  
  
if __name__ == '__main__':  
	print(basicPart.module01.var1)  
  
	print(pm2.num1)
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417043433.png)



### 1.2.2 from ... import

可以导入模块、变量或函数。

```ad-example
title: 导入模块
```

```python
from basicPart import module01  
from basicPart import module02 as pm2  
  
if __name__ == '__main__':  
	print(module01.var2)  
  
	print(pm2.num2)
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417043734.png)

```ad-example
title: 导入变量或函数
```

```python
from basicPart.module01 import var3  
  
if __name__ == '__main__':  
	print(var3)
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417043840.png)

```ad-example
title: 导入模块下的所有内容
```

```python
from basicPart.module02 import *  
  
if __name__ == '__main__':  
	print(num1)  
	print(num2)
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417044000.png)


```ad-example
title: 控制模块中对外暴露的内容
在 `module2.py` 模块中定义了 `__all__=['num1', 'num2']`，则导入模块`module2.py` 时只可导入 `num1, num2`，其他内容不可见。
```


![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417044133.png)

```ad-attention
注意，`__all__`属性仅在使用`import *`时才有效。
```

```python
from basicPart.module02 import num3  
  
if __name__ == '__main__':  
	print(num3)
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417044244.png)

```ad-example
title:导入模块换行
```

```python
from basicPart.module02 import num1, \  
num2, num3  
  
if __name__ == '__main__':  
	print(num3)
```

> 推荐使用 （） 进行组织导入

```python
from basicPart.module02 import (num1, num2, num3)  
  
if __name__ == '__main__':  
	print(num3)
```


### 1.2.3 包和模块导入注意点

-   包和模块不会重复导入：在导入一个模块的时候，就会执行这个模块里的所有内容，但是多次导入只执行一次。
-   不建议循环引入：多个模块文件间不建议相互调用，会导致报错。

### 1.2.4 相对导入和绝对导入

-   绝对导入：必须从顶级包开始。
-   相对导入：`.` 表示当前目录，`..` 上一级目录。
-   import 不能使用相对导入
-   入口文件不可以使用相对路径来导入模块，只能使用绝对路径。
-   python -m main.py 将入口文件当作一个模块执行，则可以使用相对路径导入模块。

### 1.2.5 模块搜索路径

当我们导入模块时，默认情况下python解析器会搜索当前目录、已安装的内置模块和第三方模块，搜索路径存放在**sys模块的path**中。sys.path返回一个列表

```python
from sys import (path)  
  
if __name__ == '__main__':  
	print(path)
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417044847.png)

当我们需要添加自定义的搜索目录时，使用如下命令：

```python
path.append('自定义模块的路径')
```

### 1.2.6 模块推荐导入顺序

在文件中需要导入内置模块、第三方模块或自定义模块时，**建议的导入顺序是：

- 标准库模块
- 第三方模块
- 自定义模块

## 1.3 `__init__.py` 文件的用法

-   用来标识该文件夹是一个包。
-   导入包或包下的模块时，`__init__.py` 文件被自动执行。
-   `__init__.py` 文件中也可以利用 `__all__` 来限制导入的模块。

```ad-example
title: __init__.py 文件的基本使用
例如，在`__init__.py`定义如下内容：
```

```python
__all__ = ['module01']
```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417045410.png)

由于在`__init__.py`文件中限制了导入的模块，`module2.py`不能被导入。

```ad-example
title: 批量导入
如果在项目中有模块是多个文件共用的，可以把这些模块在`__init__.py`导入。
```

## 1.4 入口文件

Python 是脚本语言，和 C++、Java 最大的不同在于，不需要显式提供 main() 函数入口。在Python文件中，`__name__ == '__main__'` 被用于定义入口文件。这些文件既可以作为模块被导入，也可以执行。

```python
 if __name__ == '__main__':
     pass
```

- 如果文件作为模块被导入，`__name__` 被赋值模块的名字。
- 当文件执行被执行时，`__name__` 为 `__main__`。



