> A Vue.js project
        
通过 Vue 以及 Element UI 搭建博客。Webpack 设置沿用 Vue 官网示例。

## Vue Router

通过 Vue Router 开发导航栏。

## CSS

利用 sass 将 color 以及 font-family 抽离成单独的文件，存放在 /src/sass-global 目录底下，并利用 sass-resources-loader 插件加载到全局。

将 /build/util.js 中 cssLoaders 的返回中加入 sass-resources-loader:
