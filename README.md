# blog

> a demo of my blog website vue project

网站页面设计借鉴 @viosey 的网站 [blog.viosey.com](https://blog.viosey.com)

**源码：** [phoeninee/phoenine](https://github.com/phoeninee/phoenine)

## 功能

1. 展示关联的github的所有库信息
2. 展示编辑好的文章

## 可配置

通过 config.json （在生产环境将会被直接复制到根目录）设置博客信息：

	{
	  // 显示在博客中的名字
	  "username": "Phoenine",
	  // github用户名
	  "gitUsername": "Phoeninee",
	  // 文章读取路径
	  "articleBasePath": "/source",
	  // about信息路径
	  "aboutMePath": "/about_me",
	  
	  // 主要图片的路径
	  "imgPaths": {
	    // 头像
	    "avatar": "/static/img/avatar.png",
	    // 默认的repository卡片logo
	    "default": "/static/img/logo.png",
	    // home页面右侧logo图片
	    "logo": "/static/img/logo.png",
	    // 主侧边栏header背景图片
	    "sidebar": "/static/img/bg1.jpg",
	    // home页面左侧motto背景图片
	    "motto": "/static/img/bg2.jpg"
	  },

	  "repoLogos": {
	    "Tetris": "/static/img/logo/Tetris.png"
	  }
	}

### github信息

通过 config.json 中的 gitUsername，使用 git API 获得 git repository 的信息

config.json 中的repoLogos项表示想要在repository卡片中显示的logo。在加载过程中会先用repository的名字检查是否有这项设置。若没有则加载默认图片。

### 文章编辑界面

简单的编辑功能，目前主要是用来生成文章的配置文件，相关格式见 [source](source/) 中的 source.json。目前只支持自动下载生成的文章（可选）以及相关配置文件。需要手动将这些信息放到相应设置的文章读取路径：

- 文章需要放在[文章读取路径] / [生成配置信息时的年份] / [相应的月份] /
 路径下，文章名需与你在配置文件中的名字一致。
- 文件配置信息需添加到 [文章读取路径] / source.json 文件中

## 使用

使用过程会用到 git，如需要了解，请移步[Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/)

### 第一步

在git命令行中输入

	git clone git@github.com:phoeninee/blog.github.io

或直接download

### 第二步

创建一个库，或选定一个已有的库将文件传上去。

请确保相关的库的git pages已开启。该选项在settings/GitHub Pages下开启。

### 关于文件

- about_me中的文件内容与“关于我”页面有关。
- source 中的文件均为相关的文章。
- static/img 目录下存放的图片可自行更改。请确保config.json中的图片路径都有对应的图片。

请下载完之后自行更改以上文件。

## issues

1. 由于是使用vue-router开发的，网站运行过程中生成的路径都是动态的。也就是说如果**直接以路径访问网站的某个具体内容**，或是**在某个具体内容上刷新**，都将得到404错误。目前正在改善中。