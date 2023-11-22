## 简介
qiankun 是一个基于 [single-spa](https://github.com/CanopyTax/single-spa) 的[微前端](https://micro-frontends.org/)实现库
微前端架构旨在解决单体应用在一个相对长的时间跨度下，由于参与的人员、团队的增多、变迁，从一个普通应用演变成一个巨石应用([Frontend Monolith](https://www.youtube.com/watch?v=pU1gXA0rfwc))后，随之而来的应用不可维护的问题。这类问题在企业级 Web 应用中尤其常见。
## 主应用
不限技术栈，这里我用的是create-react-app创建的react应用
### 安装qiankun
```bash
$ yarn add qiankun # 或者 npm i qiankun -S
```
### 在主应用注册微应用
这里我使用vue2项目为主应用
```bash
import { registerMicroApps, start } from 'qiankun';

registerMicroApps([
  {
    name: 'react-app', // app name registered
    entry: '//localhost:7100',
    container: '#yourContainer',
    activeRule: '/yourActiveRule',
  },
  {
    name: 'vue2-app',
    entry: { scripts: ['//localhost:7100/main.js'] },
    container: '#yourContainer2',
    activeRule: '/yourActiveRule2',
  },
]);

start();
```
## 子应用
分别是react、vue2、vue3、jquery四个应用
