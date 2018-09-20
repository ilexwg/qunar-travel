



## 1. 确定安装node.js

```bash
node -v
# -> v9.11.1
```

```bash
npm -v
# -> 6.4.1
```



## 2. Git

仓库地址:

https://github.com/ilexwg/qunar-travel.git



## 3. Vue脚手架安装

安装vue-cli

```bash
npm install -g @vue/cli
```

check

```bash
vue --version
# -> 2.9.6
```



## 4. 初始化项目

```bash
vue init webpack <project name>
```



## 5. 启动项目

```bash
npm run dev
```

在浏览器中输入:

http://localhost:8080

显示Vue项目的默认界面

![image-20180918213857493](./assets/image-20180918213857493.png)



## 6. 项目代码初始化

```html
<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">
```



## 7. 引入常用css文件和js文件

重置样式

reset.css:

https://pan.baidu.com/s/1qIqRVZG2c0-vy1udZkUKxw



解决1像素边框问题

border.css:

https://pan.baidu.com/s/1CYuqpME-HCmzD9gYx-Hspg



解决click事件300ms延迟问题

安装fastclick库

```bash
npm install fastclick --save
```

main.js文件中添加两行

```javascript
import Vue from 'vue'
import App from './App'
import router from './router'
import fastClick from 'fastclick' // 增加此行
import './assets/styles/reset.css'
import './assets/styles/border.css'

Vue.config.productionTip = false
fastClick.attach(document.body) // 增加此行

/* eslint-disable no-new */
new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>'
})
```



## 8. 准备iconfont

http://www.iconfont.cn



## 9. 安装stylus

```bash
npm install stylus --save
npm install stylus-loader --save
```



## 10. 添加目录别名

修改`build`目录下的`webpack.base.conf.js`文件

```javascript
'use strict'
const path = require('path')
const utils = require('./utils')
const config = require('../config')
const vueLoaderConfig = require('./vue-loader.conf')

function resolve (dir) {
  return path.join(__dirname, '..', dir)
}

const createLintingRule = () => ({
  test: /\.(js|vue)$/,
  loader: 'eslint-loader',
  enforce: 'pre',
  include: [resolve('src'), resolve('test')],
  options: {
    formatter: require('eslint-friendly-formatter'),
    emitWarning: !config.dev.showEslintErrorsInOverlay
  }
})

module.exports = {
  context: path.resolve(__dirname, '../'),
  entry: {
    app: './src/main.js'
  },
  output: {
    path: config.build.assetsRoot,
    filename: '[name].js',
    publicPath: process.env.NODE_ENV === 'production'
      ? config.build.assetsPublicPath
      : config.dev.assetsPublicPath
  },
  resolve: {
    extensions: ['.js', '.vue', '.json'],
    alias: {
      'vue$': 'vue/dist/vue.esm.js',
      '@': resolve('src'),
      'styles': resoolve('src/assets/styles'), // 在此处添加styles的路径别名
    }
  },
  module: {
    rules: [
      ...(config.dev.useEslint ? [createLintingRule()] : []),
      {
        test: /\.vue$/,
        loader: 'vue-loader',
        options: vueLoaderConfig
      },
      {
        test: /\.js$/,
        loader: 'babel-loader',
        include: [resolve('src'), resolve('test'), resolve('node_modules/webpack-dev-server/client')]
      },
      {
        test: /\.(png|jpe?g|gif|svg)(\?.*)?$/,
        loader: 'url-loader',
        options: {
          limit: 10000,
          name: utils.assetsPath('img/[name].[hash:7].[ext]')
        }
      },
      {
        test: /\.(mp4|webm|ogg|mp3|wav|flac|aac)(\?.*)?$/,
        loader: 'url-loader',
        options: {
          limit: 10000,
          name: utils.assetsPath('media/[name].[hash:7].[ext]')
        }
      },
      {
        test: /\.(woff2?|eot|ttf|otf)(\?.*)?$/,
        loader: 'url-loader',
        options: {
          limit: 10000,
          name: utils.assetsPath('fonts/[name].[hash:7].[ext]')
        }
      }
    ]
  },
  node: {
    // prevent webpack from injecting useless setImmediate polyfill because Vue
    // source contains it (although only uses it if it's native).
    setImmediate: false,
    // prevent webpack from injecting mocks to Node native modules
    // that does not make sense for the client
    dgram: 'empty',
    fs: 'empty',
    net: 'empty',
    tls: 'empty',
    child_process: 'empty'
  }
}
```



## 11. 安装vue-awesome-swiper插件

```bash
npm install vue-awesome-swiper@2.6.7 --save
```



## 12. 安装axios

```bash
npm install axios --save
```



## 13. mock文件

将mock数据(如index.json等)放在static目录下的mock目录中, 用于模拟发送AJAX请求

修改config目录下的index.js文件

```javascript
proxyTable: { // 在proxyTable中增加如下代码
      '/api': {
        target: 'http://localhost:8080',
        pathRewrite: {
          '^/api': '/static/mock'
        }
      }
    },
```



## 14. 安装better-scroll

```bash
npm install better-scroll --save
```



## 15. 安装vuex

```bash
npm install vuex --save
```

