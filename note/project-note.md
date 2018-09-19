



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

![image-20180918213857493](/Users/vonzee/gitRepos/qunar-travel/note/assets/image-20180918213857493.png)



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

