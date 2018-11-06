# Quick Start

> 在开始之前，推荐先学习 [Vue](https://cn.vuejs.org/) 、 [ES2015+](http://es6.ruanyifeng.com/) 、 [iView](https://www.iviewui.com/) , [Vue CLI 3](https://cli.vuejs.org/zh/)，并正确安装和配置了 [Node.js](https://nodejs.org/) v8 或以上 、[Git](https://git-scm.com/)。提前了解和学习这些知识会非常有帮助。

## Installation

```bash
git clone https://github.com/liuvigongzuoshi/vue-iview-admin-template my-project
cd my-project
```

## Scaffolding

应用的目录结构如下

```bash
├─dist/                   # 生产环境构建目录
├─public/                 # 主页模板目录
├─src/                    # 源码目录
│    ├─api/               # 数据接口目录
│    ├─assets/            # 静态资源文件目录
│    ├─components/        # 全局公用组件目录
│    ├─config/            # 项目URL配置目录
│    ├─router/            # 路由配置目录
│    ├─store/             # Vuex配置目录
│    ├─styles/            # 项目样式目录
│    ├─utils/             # 工具函数目录
│    └─views/             # 页面容器组件目录
│        ├─dashboard/     # 监控分析页
│        ├─layout/        # 布局组件
│        ├─log/           # 日志管理
│        │  ├─db-log/     # 用户登陆日志页
│        │  └─login-log/  # 数据库操作日志页
│        ├─login/         # 登陆页
│        ├─permission/    # 权限管理
│        │  ├─role-manage/  # 角色管理页
│        │  └─user-manage/  # 用户管理页
│        └─personal/        # 个人中心
│            ├─admin-center/ # 信息修改页
│            └─admin-log/    # 登陆记录页
├─.eslintignore           # 指定 eslint 忽略的文件
├─.eslintrc.js            # 配置 eslint 的检测规则
├─.gitignore              # Git 提交忽略的文件配置
├─.postcss.js             # 转换 css 的工具配置文件
├─.prettierignore         # Prettier忽略文件配置
├─.prettierrc             # Prettier配置
├─babel.config.js         # babel 编译配置
├─package-lock.json       # 用来锁定依赖的版本号（NPM 自动生成）
├─package.json            # 项目基本信息
├─README.md               # 项目介绍
├─vue.config.js           # 项目打包配置文件
```

## Kills

* CSS
  * less
  * flex

* JS
  * ES7 promise.finally  
  * ES7 async

* UI Library
  * iview

* JS Library
  * axios
  * echarts
  * js-cookie
  * countup

* Frame
  * Vue
  * Vue-Router @3.0+
  * Vuex 

* Project Automation 
  * webpack @4.0+
  * vue-loader @15.0+
  * babel @7.0+
  * eslint
  * prettier
  * postcss
    * autoprefixer 
  * vue-cli @3.0+

## Development

1. 进入目录安装依赖，国内用户推荐使用 [cnpm](https://cnpmjs.org) 进行加速

```bash
yarn install
```

或者

```bash
npm install
```

2. 启动本地服务器

```bash
npm run start
```

3. 启动完成后打开浏览器访问 [http://localhost:8000](http://localhost:8000)，如果需要更改启动端口，可在 `vue.config.js` 文件中配置。