

```ad-summary
title:概述
记录 Docsify 入门--用于搭建项目文档
```

# Docsify 入门

```ad-tip
title:INFO
作者：Cola

时间：2023-04-17 06:20 
```

```ad-todo
title:Features： 🐔
 - [x] Docsify 博客的搭建以及使用
 - [x] 项目配置
 - [x] 插件安装
 - [x] 通过 GithubPage 进行部署
```

## 一、Docsify 博客的搭建以及使用

### 1.1 项目搭建

#### 1.1.1 安装 node.js 和 npm

```ad-caution
title: 也可以使用 nvm 来进行安装
nvm （node version manager）是一款 node 版本管理工具，可用于同时安装不同版本的 node 并支持快速切换，具体请参见 [[Nvm 的安装与使用]]
```

> **Nodejs：** 是一个基于Chrome V8引擎的JavaScript运行环境，是一个让JS运行在服务端的开发平台，Nodejs对JS有着巨大的提升，对于前端来说，最重要的一点就是它建立了一个生态环境 **Npm**:   node package manager，即 node 环境下的一个包管理工具）

- 进入 [Node.js官网](https://nodejs.org/en/) 选择 LTS 即稳定版进行下载

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417062726.png)

- 添加环境变量

> 这种方式下载的 node.js 会自动进行环境变量的配置

- 测试

> 在控制台 cmd 中输入 `node -v` 如果输出对应的版本号即安装成功
>
> node.js 默认自带 npm ，我们可以输入 `npm -v` 来检测 npm 是否安装成功

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417062750.png)

#### 1.1.2 安装 docsify

> docsify 是一个神奇的文档网站生成器，可以快速的生成文档网站

- 我们可以使用 npm 全局安装  `docsify-cli` 工具

```bash
npm i docsify-cli -g

```

#### 1.1.3 启动本地项目并初始化

> 如果想在项目的 `./docs` 目录里写文档，可直接通过 `init` 初始化项目。

- 初始化

在工作文件夹中输入初始化命令

```bash
docsify init ./docs

```


![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417062824.png)


> - `index.html` 入口文件
> - `README.md` 会做为主页内容渲染
> - `.nojekyll` 用于阻止 GitHub Pages 忽略掉下划线开头的文件

- 启动本地项目

```bash
docsify serve docs

```

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417062933.png)

![](https://cola-picgo-1311841992.cos.ap-beijing.myqcloud.com/20230417062955.png)


## 二、项目配置

### 2.1 配置项

#### 2.1.1 name

> - 类型：`String`
>
> 文档标题，会显示在侧边栏顶部。

```js
window.$docsify = {
  name: 'docsify',
};
```

#### 2.1.2 repo

> - 类型：`String `
> - 默认值: `null`
>
> 配置仓库地址或者 `username/repo` 的字符串，会在页面右上角渲染一个 **GitHub Corner** 挂件。

```js
window.$docsify = {
  repo: 'https://gitee.com/cola0223/HelloJinZhongForC_Document/tree/master',
};
```

#### 2.1.3 maxLevel

> - 类型：`Number`
> - 默认值: `6`
>
> 默认情况下会抓取文档中所有标题渲染成目录，可配置最大支持渲染的标题层级。

```js
window.$docsify = {
  maxLevel: 6,
};
```

#### 2.1.4 loadNavbar

> - 类型：`Boolean|String`
> - 默认值: `false`
>
> 加载**自定义导航栏**，设置为 `true` 后会加载 `_navbar.md` 文件，也可以自定义加载的文件名。

```js
window.$docsify = {
  // 加载 _navbar.md
  loadNavbar: true,

  // 加载 nav.md
  loadNavbar: 'nav.md',
};
```

#### 2.1.5 coverpage

> - 类型：`Boolean|String`
> - 默认值: `false`
>
> 启用封面页,开启后是加载 `_coverpage.md` 文件，也可以自定义文件名。

```js
window.$docsify = {
  coverpage: true,

  // 自定义文件名
  coverpage: 'cover.md',

  // 多个封面页
  coverpage: ['/', '/zh-cn/'],

  // 多个封面页，并指定文件名
  coverpage: {
    '/': 'cover.md',
    '/zh-cn/': 'cover.md',
  },
};
```

#### 2.1.6 logo

> - 类型: `String`
>
> 在侧边栏中出现的网站图标，你可以使用 `CSS`来更改大小

```js
window.$docsify = {
  logo: '/_media/favicon.ico',
};
```

## 三、插件

### 3.1 emoji

> 默认是提供 emoji 解析的，能将类似 `:100:` 解析成 💯。但是它不是精准的，因为没有处理非 emoji 的字符串。如果你需要正确解析 emoji 字符串，你可以引入这个插件。

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js"></script>

```

### 3.2 图片缩放 Zoom Image

> Medium's 风格的图片缩放插件. 基于 [medium-zoom](https://github.com/francoischalifour/medium-zoom)。

```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/zoom-image.min.js"></script>

```

### 3.3 Click To Copy

> 在所有的代码块上添加一个简单的 `Click to copy`按钮来允许用户从你的文档中轻易地复制代码。由[@jperasmus](https://github.com/jperasmus)提供。

```html
<script src="//cdn.jsdelivr.net/npm/docsify-copy-code/dist/docsify-copy-code.min.js"></script>

```

### 3.3 Count Numbers

> 这是一款为docsify提供文字统计的插件. [@827652549](https://github.com/827652549)提供
>
> 它提供了统计中文汉字和英文单词的功能，并且排除了一些markdown语法的特殊字符例如*、-等

```html
<script src="//unpkg.com/docsify-count/dist/countable.js"></script>
```

```js
window.$docsify = {
  count:{
    countable:true,
    fontsize:'0.9em',
    color:'rgb(90,90,90)',
    language:'chinese'
  }
}
```

### 3.4 代码高亮

> **docsify**内置的代码高亮工具是 [Prism](https://github.com/PrismJS/prism)。Prism 默认支持的语言如下：
>
> - Markup - `markup`, `html`, `xml`, `svg`, `mathml`, `ssml`, `atom`, `rss`
> - CSS - `css`
> - C-like - `clike`
> - JavaScript - `javascript`, `js`
>
> [添加额外的语法支持](https://prismjs.com/#supported-languages)需要通过CDN添加相应的[语法文件](https://cdn.jsdelivr.net/npm/prismjs@1/components/) :

```html
  <script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-php.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-java.min.js"></script>
  <script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-python.min.js"></script>

```

### 3.5 Gitalk

> [Gitalk](https://github.com/gitalk/gitalk)，一个现代化的，基于Preact和Github Issue的评论系统。

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/gitalk/dist/gitalk.css">

<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/gitalk.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/gitalk/dist/gitalk.min.js"></script>
<script>
  const gitalk = new Gitalk({
    clientID: 'Github Application Client ID',
    clientSecret: 'Github Application Client Secret',
    repo: 'Github repo',
    owner: 'Github repo owner',
    admin: ['Github repo collaborators, only these guys can initialize github issues'],
    // facebook-like distraction free mode
    distractionFreeMode: false
  })
</script>
```

## 四、通过 GitHubPages 部署

> 和 GitBook 生成的文档一样，我们可以直接把文档网站部署到 GitHub Pages 或者 VPS 上。
>
> GitHub Pages 支持从三个地方读取文件
>
> - `docs/` 目录
> - master 分支
> - gh-pages 分支
>
> 我们推荐直接将文档放在 `docs/` 目录下，在设置页面开启 **GitHub Pages** 功能并选择 `master branch /docs folder` 选项。
