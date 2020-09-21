# 如何添加一个好看的徽章

### 1.前言

平时在逛Github的时候都经常看到项目首页各式各样的徽章：

`vue` : ![](https://img.shields.io/circleci/project/github/vuejs/vue/dev.svg?sanitize=true) ![](https://img.shields.io/codecov/c/github/vuejs/vue/dev.svg?sanitize=true) ![](https://img.shields.io/npm/dm/vue.svg?sanitize=true")

`React` : [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/facebook/react/blob/master/LICENSE) [![npm version](https://img.shields.io/npm/v/react.svg?style=flat)](https://www.npmjs.com/package/react) [![CircleCI Status](https://circleci.com/gh/facebook/react.svg?style=shield&circle-token=:circle-token)](https://circleci.com/gh/facebook/react) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://reactjs.org/docs/how-to-contribute.html#your-first-pull-request)

`Angular` : [![CircleCI](https://circleci.com/gh/angular/angular/tree/master.svg?style=shield)](https://circleci.com/gh/angular/workflows/angular/tree/master) [![Join the chat at https://gitter.im/angular/angular](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/angular/angular?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![npm version](https://badge.fury.io/js/%40angular%2Fcore.svg)](https://www.npmjs.com/@angular/core)

那么这些徽章是怎么生成的呢？

### 2.什么是徽章

徽章的本质是一种生成 `svg` 的矢量图标，无论如何如何放大缩小都不会失真

其本质上和插入图片的原理一样，变得更加精巧细致，适用于多种情况

### 3.如何使用徽章

首先需要生成自己喜欢的 `svg` 徽章文件

徽章的常用格式：`[![徽章的描述](svg或者png文件的链接)`](想要跳转的超链接)

采用 `Markdown` 格式：[![我是徽章](https://img.shields.io/badge/JeffreyYou%E7%9A%84-GitHub-brightgreen)](https://github.com/JeffreyYou/My_Documentation)

`[![我是徽章](https://img.shields.io/badge/JeffreyYou%E7%9A%84-GitHub-brightgreen)](https://github.com/JeffreyYou/My_Documentation)`

采用 `HTML` 格式：<a href="https://github.com/JeffreyYou/My_Documentation"><img src="https://img.shields.io/badge/JeffreyYou%E7%9A%84-GitHub-brightgreen"></a>

`<a href="https://github.com/JeffreyYou/My_Documentation"><img src="https://img.shields.io/badge/JeffreyYou%E7%9A%84-GitHub-brightgreen" alt="我是徽章"></a>`

### 4.如何生成自己喜欢的徽章

https://shields.io/

该网站适用于绝大多数情况,默认按照徽章内容分类

`Build`,`Code Coverage`,`Analysis` 等多主题,同时支持自定义徽章和动态徽章.



以 `create-react-app` 为例，我们要展示它的开源许可证

`create-react-app`  是Facebook为了方便开发者搭建 `react` 项目开发环境的手脚架

首先进入官网选择 `License`  -- `npm` 

然后输入 `packageName` `create-reacte-app`

<div align=center><img width="450"  src="https://github.com/JeffreyYou/My_Documentation/blob/master/images/Badges/20200921153812.png"/></div>

`Copy Badge URL` ，表示MIT开源许可的徽章就生成了

### 5.自定义Style

|      |               常见命令                |                           命令含义                           |                             补充                             |
| ---- | :-----------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| 1.   |        `?label=healthinesses`         |             将徽章左边的内容改成`healthinesses`              |                              /                               |
| 2.   |           `?logo=appveyor`            |        添加自己想要的[Logo](https://simpleicons.org/)        |                              /                               |
| 3.   |    `?logo=data:image/png;base64,…`    |                   自定义logo (≥ 14px high)                   | There is a limit on the total size of request headers we can accept (8192 bytes). |
| 4.   |          `?logoColor=violet`          |                        改变logo的颜色                        |      支持hex, rgb, rgba, hsl, hsla and css named colors      |
| 5.   |            `?logoWidth=40`            |                      设置logo的水平长度                      |                              /                               |
| 6.   | `?link=http://left&link=http://right` |                   单独设置徽章左侧的超链接                   |                              /                               |
| 7.   |         `?labelColor=abcdef`          |                       修改左侧背景颜色                       |         The legacy name "colorA" is also supported.          |
| 8.   |            `?color=fedcba`            |                       修改右侧背景颜色                       |         The legacy name "colorB" is also supported.          |
| 9.   |         `?cacheSeconds=3600`          | Set the HTTP cache lifetime The legacy name "maxAge" is also supported. | rules are applied to infer a default value on a per-badge basis, any values specified below the default will be ignored. |

### 5.自定义徽章展示


|        展示        |                             效果                             |
| :----------------: | :----------------------------------------------------------: |
|   那个绿色的男人   | [![](https://img.shields.io/badge/G%E8%83%96%E8%BF%98%E6%88%91-%E8%A1%80%E6%B1%97%E9%92%B1%EF%BC%81-orange?logo=steam)](https://github.com/JeffreyYou/My_Documentation) |
|  求求了给个三连吧  | [![](https://img.shields.io/badge/下次-一定-orgreen?logo=Bilibili)](https://github.com/JeffreyYou/My_Documentation) |
| I love open source | [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badge/) |
|  充钱就能变得更强  | [![](https://img.shields.io/badge/你在想-Peach-red?logo=Tencent-QQ)](https://github.com/JeffreyYou/My_Documentation) |
| 最大的同性交流网站 | [![](https://img.shields.io/badge/%E6%B2%A1%E9%94%99-%E5%B0%B1%E6%98%AF%E6%88%91-lightgrey?logo=Github)](https://github.com/JeffreyYou/My_Documentation) |


<table align=center>
<thead>
<tr><th style='text-align:center;' >展示</th><th style='text-align:center;' >效果</th></tr></thead>
<tbody><tr><td style='text-align:center;' >那个绿色的男人</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/G%E8%83%96%E8%BF%98%E6%88%91-%E8%A1%80%E6%B1%97%E9%92%B1%EF%BC%81-orange?logo=steam" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >求求了给个三连吧</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/下次-一定-orgreen?logo=Bilibili" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >I love open source</td><td style='text-align:center;' ><a href='https://github.com/ellerbrock/open-source-badge/'><img src="https://badges.frapsoft.com/os/v1/open-source.svg?v=103" referrerpolicy="no-referrer" alt="Open Source Love"></a></td></tr><tr><td style='text-align:center;' >充钱就能变得更强</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/你在想-Peach-red?logo=Tencent-QQ" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >最大的同性交流网站</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/%E6%B2%A1%E9%94%99-%E5%B0%B1%E6%98%AF%E6%88%91-lightgrey?logo=Github" referrerpolicy="no-referrer"></a></td></tr></tbody>
</table>

![](https://github.com/JeffreyYou/My_Documentation/blob/master/images/Badges/svg/iconmonstr-favorite-1.svg)

[![](https://img.shields.io/badge/你在想-Peach-red?logo=https://github.com/JeffreyYou/My_Documentation/blob/master/images/Badges/svg/iconmonstr-favorite-1.svg)](https://github.com/JeffreyYou/My_Documentation)

[![](https://img.shields.io/badge/你在想-Peach-red?logo=data:image/png;base64,…)](https://github.com/JeffreyYou/My_Documentation)

