# 配置项

你可以在 `/src/utils/config.js` 里做一些自定义配置：

## siteName

- 类型： `String`

  配置站点名称，应用到登录框，侧边栏顶部的标题文字显示。

## copyright

- 类型： `String`

  配置版权声明，应用到登录页、`Primay`布局底部。

## logoPath

- 类型： `String`

  配置站点 Logo，应用到登录框，侧边栏顶部的 Logo 显示。

## apiPrefix

- 类型： `String`

  配置项目中接口的前缀，接口相关文档可查看 [接口配置化]()

## fixedHeader

- 类型： `String`

  在`Primary`布局下，页面滚动时是否固定顶部。

## layouts

- 类型： `Array`

    配置哪些路由使用哪种布局，未指定路由使用默认布局 `Public`，项目中目前有 `Primary` 和 `Public` 两种布局，
    默认配置如下：
  
    ```js
        layouts: [
            {
                name: 'primary',
                include: [/.*/],
                exlude: [/(\/(en|zh))*\/login/],
            },
        ],
    ```

    每种布局的对象属性如下：

    - `name` - 布局的名称；
  
    - `include` - 指定使用该布局的路由规则列表，规则可为正则表达式或者字符串；
  
    - `exlude` - 指定不使用该布局的路由规则列表，规则可为正则表达式或者字符串。
  
 > 注意：`exlude` 优先级高于 `include`，后面的布局优先级高于前面的布局。开发过程中可能需要结合`src/layouts`目录下的布局使用，具体方法可查看 [使用布局]()。

## i18n

- 类型： `Object`

  配置国际化，默认配置如下：

  ```js
  i18n: {
      languages: [
        {
            key: 'en',
            title: 'English',
            flag: '/america.svg',
        },
        {
            key: 'zh',
            title: '中文',
            flag: '/china.svg',
        },
      ],
      defaultLanguage: 'en',
  }
  ```

  ### i18n.languages

  - 类型： `Array`

    指定应用支持哪些语言，每种语言的对象属性如下：

    - `key` - 语言的`key`，应用到页面 url 上以区分语言，也对应 `src/locales` 目录下的语言包文件夹名；

    - `title` - 语言名称，在登录页底部、`Primay` 布局顶部语言切换显示；

    - `flag` - 语言的国旗图标的路径，在 `Primay` 布局顶部语言切换显示。

 ### i18n.defaultLanguage
   
   - 类型： `String`

        配置默认语言。

## Layout

## Router

## Code Standards

* 组件相关
    * 只要有能够拼接文件的构建系统，每个组件单独分成文件
    * 单文件组件的文件名要么单词大写开头 (PascalCase)，要么横线连接(kebab-case)并组件名完整单词而不缩写
    * 组件名应该以高级别的单词开头，以描述性的修饰词结尾，以大驼峰命名
    * 和父组件紧密耦合的子组件应该以父组件名作为前缀命名
    * vue 单文件中的 `<template>、<script>、<style>` 标签的顺序
    * 组件/实例的选项应该有统一的顺序，每个选项增加一个空行隔开，增加可读性
    * Vue 组件中 `<template> Html` 过长，换行展示
    * Vue 中监听的事件记得垃圾回收
    * Vue 组件中不要直接操作异步请求，把所有的异步请求方法封装成一个独立 js 文件，或者放到 Vuex 中
* CSS相关
    * 使用 [BEM](https://en.bem.info/) 命名规范来组织CSS代码，谨慎使用 `scoped` 
    * 容器组件 `CSS` 命名 `容器名-wrapper`
* 备注 
    * 代码中不用的注释都删掉
    * 调试结束，把不用的 console.log(...) 及时删掉，它会影响性能 
* 其他
    * 所有命名语义化命名 
    * `Commit` 代码之前，[一定要先效验与格式化代码](#Lints-and-fixes-files)，没有问题再提交
    * [BEM的定义](https://www.w3cplus.com/css/bem-definitions.html)
    * [使用BEM命名规范来组织CSS代码](https://zhuanlan.zhihu.com/p/46073785)
    * 更多 Standards 参考[ Vue 官方的特有代码的风格指南](https://cn.vuejs.org/v2/style-guide/)