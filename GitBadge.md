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

1. https://shields.io/

   该网站适用于绝大多数情况,默认按照徽章内容分类

   `Build`,`Code Coverage`,`Analysis` 等多主题,同时支持自定义徽章和动态徽章.

   以 `create-react-app` 为例

   `create-react-app`  是Facebook为了方便开发者搭建 `react` 项目开发环境的手脚架

   首先进入官网选择 `License`  -- `npm` 

   ![](https://github.com/JeffreyYou/My_Documentation/blob/master/images/Badges/20200921155449.png)

   输入 `packageName` `create-reacte-app`

   ![](https://github.com/JeffreyYou/My_Documentation/blob/master/images/Badges/20200921153812.png)

   `copy Url` 

