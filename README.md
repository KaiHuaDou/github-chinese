# [GitHub 中文化插件][project-url]

> 本项目源自: [52cik/github-hans](https://github.com/52cik/github-hans)

  [![GitHub issues][issues-image]][issues-url]
  [![GitHub stars][stars-image]][stars-url]
  [![GitHub forks][forks-image]][forks-url]
  [![license GPL-3.0][license-image]][license-url]
  [![GreasyFork installs][greasyFork-image]][greasyFork-url]

## 💖星标历史

<a href="https://star-history.com/#maboloshi/github-chinese&Timeline">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=maboloshi/github-chinese&type=Timeline&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=maboloshi/github-chinese&type=Timeline" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=maboloshi/github-chinese&type=Timeline" width="75%" />
  </picture>
</a>

## 🚩功能

- 中文化 GitHub 菜单栏，标题，按钮等公共组件
- 保留、完善正则功能
- 除基础组件中文化外，还支持对 “项目描述” 进行人机翻译 (参考: [k1995/github-i18n-plugin](https://github.com/k1995/github-i18n-plugin))

## 🌐 浏览器与脚本管理器

浏览器                              | 脚本管理器
:---------------------------------: | :---------: 
Chrome 或 基于 Chromium 内核的浏览器| [Tampermonkey][Tampermonkey],[violentmonkey][violentmonkey]
Safari 浏览器                       | [Macaque][Macaque]
Firefox 浏览器                      | 未测试

## 💽 安装
1. 请先安装用户脚本管理器。
1. 然后再点击链接之一，安装脚本即可。
    - [GitHub 中文化插件 - github 托管【开发版】（相对及时更新）][main.user.js]
        > 注意: 当版本号未更新的情况下, 即使内容已更新, 用户脚本管理器依然会忽略, 需要手动安装获取更新
    - [GitHub 中文化插件 - greasyfork 托管【发布版】（仅大版本更新）][main(greasyfork).user.js]
1. 刷新下页面，即可发现网站已中文化。

## 📝 更新说明

### 2023-08-31 13:39:36

更新至 1.8.5

1. 优化: `transDesc 函数`代码
1. 修复: 重复添加`translate-me`翻译按钮
1. 加强：`watchUpdate 函数`新增节点文本更新的情况
1. 调整: `transBySelector和transDesc函数`延迟执行时间
1. 更新: 忽略规则, 词条等

### 2023-08-08 11:53:03

更新至 1.8.4

1. 修复: `Itemprop`过滤规则, 依然使用正则方式
1. 修复: `tooltipped`样式提示, 依然使用正则方式

### 2023-08-07 14:41:17

更新至 1.8.3

1. 梳理、优化脚本
1. 更新: 忽略规则, 大量词条等

### 2023-05-15 18:02:04

更新至 1.8.2

1. `greasyfork 托管`源切换到`按页面精细化词条模式`
1. 调整词库格式
1. 功能加强: 优化`元素筛选器`翻译逻辑
1. 更新: 忽略规则, 大量词条等

### 2023-01-22 22:01:39

更新至 1.8.1

1. 修复: #8 与 dark reader 扩展发生冲突，导致时间显示出现问题
1. `GitHub`源开始切换到`按页面精细化词条模式(开发版)`, 词库未完全迁移适配
1. 停止`greasyfork`源词库文件的同步更新

### 2023-01-18 12:56:24

更新至 1.8.0

1. 删除: `TURBO-FRAME`框架处理代码. Github 已调整新动态加载模式, 直接检测`url`的变化就能获取对应的`page`信息
1. 新增: 支持时间元素的`Shadow DOM`翻译, 并监听变化
1. 新增: 启用并更新`时间元素翻译`专项正则词条
1. 新增: 仅当`page`有效才翻译页面
1. 修复: 原`简介翻译`引擎`GitHub中文社区`失效, 改为`讯飞`引擎(测试)
1. 修复: 追加公共正则重复迭代的问题
1. 修复: 正则标记变量`RegExp`与构造函数`new RegExp`冲突
1. 更新: 忽略规则, 词条等

预告, 下次将细化`page`匹配规则, 导致词库文件结构大调整, 词库文件会适当变大, 页面正则更精细效率会提升

<details>
  <summary><h3>💠 更多... </h3></summary>

### 2022-07-17 14:04:44

更新至 1.7.9

GitHub 的 ajax 载入方式逐步从 [defunkt/jquery-pjax](https://github.com/defunkt/jquery-pjax) 切换到 [hotwired/turbo](turbo.hotwired.dev), 导致已有的动态监测方式逐步失效

目前, 通过以下修复:

1. 新增 `BODY` 元素新增监视
1. 解析 `TURBO-FRAME` 框架, 获取对应的 `page`
1. 修复 github 新动态加载模式, 导致`翻译描述`返回值无法插入
1. 修复 github 新动态加载模式, 导致`chrome`浏览器自带翻译功能卡死页面

其他更新:

1. 修复`rePagePath`,`rePagePathRepo`,`rePagePathOrg`匹配规则，限制路径匹配层次，排除干扰
1. 直接使用网页URL`document.URL`变化触发`标题翻译`和`JS 筛选器`翻译
1. 修复`关闭正则`无法生效, 需要刷新页面才生效
1. 日常更新词库和忽略规则
1. 更新`JS 筛选器`规则

### 2022-06-29 13:27:12

更新至 1.7.8

1. 紧急修复: GitHub 变更了`document.body`和`title`更新机制, 导致原有的`监测更新`规则部分失效, 目前使用`document.documentElement`监视整个页面 DOM 的变更
2. 跳过`<HEAD>`标签
3. `标题翻译`和`JS 筛选器`翻译, 依据 URL变化更新

### 2022-06-26 16:41:58

更新至 1.7.7

1. 新增`时间元素翻译`功能
2. 重写`页面标题翻译`函数
3. 梳理`遍历节点`函数逻辑
4. 优化`transPage`函数，默认翻译公共部分
5. 调整`getPage`函数, 使`ClassName匹配规则`优先
6. 优化`translate`函数, 跳过`不存在英文字母和符号,.`, 保留首尾空白部分等
7. 部分函数重命名，使用`es6`新语法
8. 日常更新词库和忽略规则，修复一个`JS 选择器规则`

### 2022-05-12 13:53:46

更新至 1.7.6

1. 日常更新词库和忽略规则
2. 添加手动开启/禁用正则翻译，添加切换菜单
3. 优化翻译文本函数：避免已翻译词汇二次匹配，提高效率；局部翻译优先于全局

### 2022-02-26 12:36:14

更新至 1.7.5

### 2022-01-21 13:34:06

更新至 1.7.4

### 2021-12-26 12:01:11

更新至 1.7.3

### 2021-12-01 09:04:58

更新至 1.7.2

### 2021-11-23 10:51:22

更新许可证为 [GPL-3.0][license-url] 希望大家依据许可证使用

### 2021-10-31 21:49:00

正式发布 1.7.0 版本

### 2021-10-07 13:16:16

原作者[楼教主](https://github.com/52cik/github-hans)已停止维护多年，且近年来 GitHub 页面结构的变化，导致原有的脚本无法正常工作。

虽然 GitHub 在被微软售收购比较重视国际化，启动并基本完成了GitHub 文档的中文化。但是，关于 GitHub 页面的中文化暂时还没启动。

对于，新手使用和高阶使用仍会存在一定的障碍。故，本人依据个人兴趣暂时进行了一定的修复和维护。

本次维护基本恢复和保留大部分功能如：页面正则翻译（含日期的正则）。页面词条可能被我切得太碎不方便后期维护（先这样吧！）

</details>

## ✔待办 (TODO)

1. 添加 GitHub 名词解释，新手可能不太理解部分名词具体表达的意思，比如 `pull request`。
2. 整理部分 git & [GitHub](https://github.com/) 学习资料, 帮助新手**更快**上手。
3. **本人英文渣渣，翻译非常困难，急需大家 pr 共同翻译**

## ✨贡献

目前，已翻译大部分常用页面，欢迎补充完善，中文词条在`locals.js`中。大家在补充完善的过程，请遵循以下文档对相关术语进行翻译：

相关概念及资料文档:

1. [Pro Git 第二版 简体中文](https://www.gitbook.com/book/bingohuang/progit2/details)
2. [Pro Git: 翻译约定](https://github.com/progit/progit2-zh/blob/master/TRANSLATION_NOTES.asc)
3. [Git官方软件包的简体中文翻译](https://github.com/git/git/blob/master/po/zh_CN.po)
4. [GitHub 词汇表官方译本](https://docs.github.com/cn/get-started/quickstart/github-glossary)

## 🎨 预览

  ![github-chinese][github-chinese]

<details>
  <summary><h2>🎁 打赏</h2></summary>

  <img src="https://cdn.staticaly.com/gh/maboloshi/maboloshi/main/img/weixin.jpg" alt="微信赞赏" width="30%">  <img src="https://cdn.staticaly.com/gh/maboloshi/maboloshi/main/img/alipay.jpg" alt="支付宝赞赏" width="30%">
  
</details>

[project-url]: https://github.com/maboloshi/github-chinese "GitHub 中文化插件"

[issues-url]: https://github.com/maboloshi/github-chinese/issues "议题"
[issues-image]: https://img.shields.io/github/issues/maboloshi/github-chinese?style=flat-square&logo=github&label=Issue

[stars-url]: https://github.com/maboloshi/github-chinese/stargazers "星标"
[stars-image]: https://img.shields.io/github/stars/maboloshi/github-chinese?style=flat-square&logo=github&label=Star

[forks-url]: https://github.com/maboloshi/github-chinese/network "复刻"
[forks-image]: https://img.shields.io/github/forks/maboloshi/github-chinese?style=flat-square&logo=github&label=Fork

[license-url]: https://opensource.org/licenses/GPL-3.0  "许可证"
[license-image]: https://img.shields.io/github/license/maboloshi/github-chinese?style=flat-square&logo=github&label=License

[greasyFork-url]: https://greasyfork.org/scripts/435208  "GreasyFork - GitHub 中文化插件"
[greasyFork-image]: https://img.shields.io/badge/dynamic/json?style=flat-square&label=GreasyFork&query=total_installs&suffix=%20installs&url=https://greasyfork.org/scripts/435208.json

[Tampermonkey]: http://tampermonkey.net/ "篡改猴"
[violentmonkey]: https://violentmonkey.github.io/ "暴力猴"
[Macaque]: https://macaque.app/ "猕猴"

[main.user.js]: https://github.com/maboloshi/github-chinese/raw/gh-pages/main.user.js "GitHub 中文化插件 - GitHub 托管"
[main(greasyfork).user.js]: https://greasyfork.org/scripts/435208-github-%E4%B8%AD%E6%96%87%E5%8C%96%E6%8F%92%E4%BB%B6/code/GitHub%20%E4%B8%AD%E6%96%87%E5%8C%96%E6%8F%92%E4%BB%B6.user.js "GitHub 中文化插件 - GreasyFork 托管"

[github-chinese]: https://raw.githubusercontent.com/maboloshi/github-chinese/gh-pages/preview/github-chinese.webp
