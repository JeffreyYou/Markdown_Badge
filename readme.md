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

比较常见的网站如 [Quality metadata badges for open source projects](https://shields.io/)

该网站适用于绝大多数情况,默认按照徽章内容分类

支持 `Build`,`Code Coverage`,`Analysis` 等多主题,同时支持自定义徽章和动态徽章.

例如：

以 `create-react-app` 为例，我们要展示它的开源许可证

`create-react-app`  是Facebook为了方便开发者搭建 `react` 项目开发环境所准备的手脚架

首先进入官网选择 `License`  -- `npm` 

然后输入 `packageName` `create-reacte-app`

<div align=center><img width="400"  src="https://github.com/JeffreyYou/My_Documentation/blob/master/images/Badges/20200921153812.png"/></div>

`Copy Badge URL` ，表示MIT开源许可的徽章就生成了

### 5.如何自定义徽章的样式

|      |               常见命令                |                      命令含义                      |                            补充                             |
| ---- | :-----------------------------------: | :------------------------------------------------: | :---------------------------------------------------------: |
| 1.   |        `?label=healthinesses`         |        将徽章左边的内容改成`healthinesses`         |                              /                              |
| 2.   |           `?logo=appveyor`            | 搜寻添加自己想要的[Logo](https://simpleicons.org/) |                              /                              |
| 3.   |    `?logo=data:image/png;base64,…`    |                自定义logo (≥ 14px)                 |                整体大小不能大于 `8192 bytes`                |
| 4.   |          `?logoColor=violet`          |                   改变logo的颜色                   | 支持 `hex`, `rgb`, `rgba`,` hsl`, `hsla` ，`css named` 颜色 |
| 5.   |            `?logoWidth=40`            |                 设置logo的水平长度                 |                              /                              |
| 6.   | `?link=http://left&link=http://right` |              单独设置徽章左侧的超链接              |                              /                              |
| 7.   |         `?labelColor=abcdef`          |                  修改左侧背景颜色                  |                     可用 `colorA` 替换                      |
| 8.   |            `?color=fedcba`            |                  修改右侧背景颜色                  |                     可用 `colorB` 替换                      |
| 9.   |         `?cacheSeconds=3600`          |                设置HTTP缓存生存时间                |                     可用 `maxAge` 替换                      |
| 10.  |      `?`+`command1`+`&command2`       |               同时使多个command生效                |             注意只有一个 `?` 其余使用 `&` 连接              |

### 6.如何使用自定义logo

除了官方已经提供的 [Logo](https://simpleicons.org/) 外，我们还希望可以自己导入喜欢的logo，然而自己制作

**第一步** ：下载好自己喜欢的 `svg` / `imae` / `png` 

**第二步** ：将下载好的图片通过 [Base64转码工具](https://b64.io/) 转成一个以 `data:image/png;base64` 为开头的字符串

**第三步** ：将转义好的 `base64` 字符串通过 [百分号转码工具](https://meyerweb.com/eric/tools/dencoder/) 将一些字符如 `/` 转义成 `%2F`  的 `URL` 地址

**第四步** ：将转义好的 `URL` 按照 `?logo=URL` 的格式添加的链接的结尾

### 7.自定义logo展示

<div align=center><img src="https://img.shields.io/badge/I%20love%20you%20-three%20thound-yellow?colorA=green&logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAABeUlEQVQokb2QvUtbYRSHn3O8qQVtEm0aM9TNoSBZqi7WwRahCkLi4lAHP5YOgggiOJbiokKHFicHXYSGZiwdOnQQSykUdLEOUj9AF%2BmgkhAT731fB7nX5P4B%2BcGBcw7nOV9Qb4nvzG7ZF6J2DkxCRPIfevVT5zRNBcxbLFYER0RzR6tyEoDvf9guo%2BYXEKlqufh1A2mo6PLYJE8rSvbLpnHKnn7c3ZALBYgaMxV3icRd8M05Zyx5bXd%2Bb8rVzID8fX1Jbr5H%2F6TK3jCAAxD1aBZqZS%2BlmCzomR%2BnR%2BTfRL89S8ZkPADjLvthUG6gtVSbe%2FyQNCXdB1CAlop%2Bjnl4MQ8Cu4G2EJgomFePvrMdgC9H5Djuslp9Y2to4tpz25Uo24N3iAlWBXji6kJFvG6QXgB178F82j5zymYgu%2Bcs%2BfXqO%2B2jUoo%2BaBhsNPKt0UCze7fqzw43kyqabGZPV2p%2BEPoJ1lo5zXlvrg9k6Hyd%2FxbN9x3Kdriu%2FroF7hWIG8yVVu0AAAAASUVORK5CYII%3D"></img></div>

<div align=center><img src="https://img.shields.io/badge/I%20love%20you%20-three%20thound-red?logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAJAAAACQCAYAAADnRuK4AAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAAJMUlEQVR4nO3df5CVVR3H8ff37goSq6WluWr1B440ohBJNMC9y2IzKgM5E4gQklbUYCSIDuVYjf3UzIZRCeiHY9GAI4TbRD%2BAUZTl3gWEkQETTNF%2BMAioRGmwoMvu%2FfbH3aUNF9jdc57nPM%2B939cMw7Bwvue7cz97nsu9zz0HjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGpImEbuBk9JOczRnUIQxGGIgyEDgPeB%2FQn1Lvb7b%2FegvYjbKdDNtQtkmB%2FeG6fzfNUYswlCJDEYYCH6b0vby3%2FXcFmil9PweAF4FdwHO0UJDN%2FCdQ66eUqADpSAZQxY3AOOBKoKr3xdiB8FugQQr82VOLPWshyxCECcBEYJBDqVZgK7AKZak08TcvDXoQPEA6iSr2cwPCV4GRkfSkvAg8wFn8Wlbzjvf6naeq50yK3IxyOzAwiimAjSgLqeU3soK2CObotmAB0nqqaeMLwJ3AgJim3Q88SD8WyhM0%2ByysV9OfI9yKMAe4wGftU3gF4T4%2ByOJQQQoSIB3FMDIsAj4RYn6EvSi3SYEGH%2BU0y3iEBcBHfNTrMWE7yq1SYEP8U8dIR9CPauYBt8Q990k8ThWzpJHXejNYc9SiLGh%2FnhOaoiyimrnSyNtxTRrbg6ijGEiG5cCQuObspn0UmSgbeKYng3Q0IyjSANRG1FdvvUAVk6WRHXFMloljEh3NGDJsIXnhAbiQDI2a5YvdHaA5plHkKZIXHoDLaGOT5rgmjskiD5DmmEKRNcDZUc%2FloC%2FCI5rlm6f7h5rjbmAJ0C%2F6tnqtBlipdUyOeqJIL2GaYwrwKDGtdF4Id0me%2B7r6K81yB8K8uFtyUESYKnmWRzVBZAHSLNcirAT6RDVHhGZLgZ90%2FoLmmAM8EKgfFy1kGC%2FreTKK4pEESEcxiAybKb3lkEZFlGukibUAWsfVKKtJ00r6%2Fw4jDJc8f%2FFd2HuA9Gr6c5QtwGW%2Ba8fsDVr5OH1po41txPfiYFR2coThspUjPov6%2F4k6ygLSHx6A86lmGW2sIP3hARhEP%2Bb7Lup1BdIco4F1vusaj4RPSZ6n%2FZXzRAfRh3N4DuGjvmqaSOyihsG%2B3lT2dwk7l5kWnlS4lMN82VcxLyuQjqUvzfwV5SIf9UzkXqWGS3ysQn5WoGY%2Bb%2BFJlYs5xM0%2BCvkJkPIVL3VMfIQZfso40jquQMPcMmocCYMlz%2FMuJdxXoKKfpdAEcaNrAfcACdc61zBhqPtj53QJ05GcTxWvudYxwSgt1MpmXu9tAbcVqJp6LDxpJvQh51LALUBFrnAab8ITLncZ7hagTCSfezJxUrfH0C1AyqVO400SBAwQvN9xvAnvXJfBrgGqcRxvwjvLZbAFyAQNUKvjeBOe02PoGqDDjuNNeIdcBrsG6C3H8SY8p42rXAP0D8fxJjTl7y7D3QIkvOQ03iTBLpfBrivQC47jTWgZtw8bur4SXXAab5Ig7zLY7XYOEHIcwF6RTqt%2FUeA8gWJvCzitQFLa8HGVSw0T1GqX8ICfW1ofc65hwlCWuZZwD9DbrAXecK5j4naQf%2FOEaxHnAMlWjiH81LWOid3PZSctrkV8fS5sIXDUSy0Th2NU%2Bfmh9xIgKXAA4WEftUwMhF9JI6%2F6KOVvc4UM38feG0uDo%2B2PlRfeAiSN%2FBPlh77qmYgo83ytPuB7g6nS%2BRdbgKE%2B6xpvXqaVIbLJ3%2FNVr1vcSSOtlI4xCHqCjOmSkmGGz%2FBABHskSoEtCD%2FwXdc4e0jWs8530Wi2%2BYUMOZ4Eroqivumx56lieBSHsESy77FAkSKfA%2FZEUd%2F0yEGEiVGd4BPZxtmygX0UGUvpDFATRgsZJkmel6OaINKd12UDO8kwAdxfMjc9psD0KJ73dBb51v2ynnUIM6Oex7zLt6TA0qgnieXsB8nzCPh79dOchvALKXBvPFPFSLPciXR9lJLx5mEK3OJ6o1h3xXr6jDTxI0qnNJto%2FIwCM%2BIKD4Q6tTnLzPZTjm13M1%2BUedLE3LinDXL%2BlTSxCGEWMf6klDXhnhDhKU0dkGb5DMJS4D0h%2B0ixNoTbJM%2FCUA0Ev4RoliEIfwQuDt1LyhwCPisF%2FhSyieABAtARXEQ1f8BuA%2BkeYS%2BtjJeNbA%2FdSiLOAJVN7KWFeoTVoXtJgc1kGJaE8EBCVqAOCkKWryPcS0LCnTBLaPV%2FT4%2BLRAWog%2BYYBywBzgndS0K8A8ySQvI%2BuJDIAAFoPZfQRgMwOHQvge0BrpcCW0I30pXEXiakkVfox0hKK1GlWkMfhiY1PJDgFagzzXITwkIqZ1fYVoR7yPO9ON%2BW6I1UBAhARzGQDI9R%2Fv%2FV340wVfJsDN1IdyT2EnYi2cBL1DACYT6lm6XKUQNVfCwt4YEUrUCdaR3XofyS8tnY6ijCXZLnodCN9FQqAwSgdXyIIo8ibuddJcBOqpgijewI3UhvpOYSdiLJs4daxiB8l%2FR%2BkHEJRxie1vBAilegzrSOq1CWABeG7qWbDgLTpcDK0I24KosAAWg9H6CNxcC40L2ckvAMMFXybht8J0XZBAja30urYzbK%2FUCf0P2coIiwgGbmylaOhW7Gl7IKUAcdxTAyLAMGhO4FAOV1Mtwkefc9CZMmtU%2BiT0U28Cx9uRL4XehegDVUc3k5hgfKdAXq0OmS9mPgjNinF%2B4nzzeS%2FnaEi7IOUAetow5lOXBBTFMeRJkmTayJab5gKiJAcPy22RXAiEgnEp6lletlI7sjnSchyvI5UFdkE3upYQxE%2BnnxBpoZXSnhgQpagTq0Py%2F6Nsrd%2BPz%2Bhfnkub2cn%2B90peIC1EHrmIyyGDjTsVQLMEMKLHZuKoUqNkBw%2FC2Q3wP9e1miGeE6yfO0z77SpKIDBKBZsgir6Pn56UcQPl3J4YEKehJ9MtJEEzCWnh1%2F3UyG8ZUeHrAV6DgdTY4iqzn95ewwytj24FW8il%2BBOsh6Cgg3cOp7i9qAaRae%2F7EAdSJ5VgFfO%2Bk%2FUO4oh3t4fLJLWBc0SwPChBO%2B%2FLgUmBSkoQSzFagr1UwH9h3%2Fs7CXvnwpXEPJZQHqgjTyJsqcTl%2BaLWvtLDTTQ5qjUXM8FbqPJKsO3UCiKd9ByvZDjMYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYYyrQfwEGQyJFQbtWewAAAABJRU5ErkJggg%3D%3D"></img></div>

<div align=center><img src="https://img.shields.io/badge/I%20love%20you%20-three%20thound-red?colorB=orange&colorA=43AD8D&logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8%2F9hAAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAABkUlEQVQ4ja2Sv0tbURTHv%2Fe%2Be5%2F68kIgi2gWETu5CHXrGAiNEezaQRBdBdHB%2Fgc6Cf4DIdBFKHQITdI8p0IlIJTi0i4BURDX5JH7ou%2B9%2B8MlYkxJiMXPdDjf8zmHCxd4TUyxmDSl0uTQvFSaNMVisr9HACCu1d4R1z2gtr0MrSMt5W8IccxWVr4BgPS8D3CcHcr5EozhOorOtRCf7ELhFzGelzCue0EcZ%2BHZNSm70vd3oZTF0ukjwthUf66D4A9tNpdZbFlbfEAGAMKYw5LJw149NZjTRGIxzmQ2GGFsbtibiW2nh2W9%2FA1FGIajhkYSxxFFHNeMlPcvlrVWpNs9o3x19afudE5e6qtO5ztbW6tSALCur%2FeUEGfjyiaKLpUQ%2B0DvHwDAfaUyz1OpL9R1346Uw%2FBGtVrrPJ%2F%2F8WwBAASnp7MTnH%2B2UqksCPlH1kHwV%2Fn%2Bpl0onD%2F2aP9AIpe7tYD3st0%2BNEpFT6Y2qt3%2Beuf72X55JLJa%2FagbjaZuNK6ien17LGkQUS5PB%2FX6zH%2FJ4%2FIAd1%2BkpmPB%2FIUAAAAASUVORK5CYII%3D"></img></div>

### 8.自定义徽章展示

<table align=center>
<thead>
<tr><th style='text-align:center;' >展示</th><th style='text-align:center;' >效果</th></tr></thead>
<tbody><tr><td style='text-align:center;' >那个绿色的男人</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/G%E8%83%96%E8%BF%98%E6%88%91-%E8%A1%80%E6%B1%97%E9%92%B1%EF%BC%81-yellow?colorA=4a9718&amp;logo=steam" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >求求了给个三连吧</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/下次-一定-orgreen?logoColor=white&amp;logo=Bilibili" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >I love open source</td><td style='text-align:center;' ><img src="https://img.shields.io/badge/I%20love-Open%20Soucre-43AD8D?logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAJAAAACQCAYAAADnRuK4AAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAAJMUlEQVR4nO3df5CVVR3H8ff37goSq6WluWr1B440ohBJNMC9y2IzKgM5E4gQklbUYCSIDuVYjf3UzIZRCeiHY9GAI4TbRD%2BAUZTl3gWEkQETTNF%2BMAioRGmwoMvu%2FfbH3aUNF9jdc57nPM%2B939cMw7Bwvue7cz97nsu9zz0HjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGpImEbuBk9JOczRnUIQxGGIgyEDgPeB%2FQn1Lvb7b%2FegvYjbKdDNtQtkmB%2FeG6fzfNUYswlCJDEYYCH6b0vby3%2FXcFmil9PweAF4FdwHO0UJDN%2FCdQ66eUqADpSAZQxY3AOOBKoKr3xdiB8FugQQr82VOLPWshyxCECcBEYJBDqVZgK7AKZak08TcvDXoQPEA6iSr2cwPCV4GRkfSkvAg8wFn8Wlbzjvf6naeq50yK3IxyOzAwiimAjSgLqeU3soK2CObotmAB0nqqaeMLwJ3AgJim3Q88SD8WyhM0%2ByysV9OfI9yKMAe4wGftU3gF4T4%2ByOJQQQoSIB3FMDIsAj4RYn6EvSi3SYEGH%2BU0y3iEBcBHfNTrMWE7yq1SYEP8U8dIR9CPauYBt8Q990k8ThWzpJHXejNYc9SiLGh%2FnhOaoiyimrnSyNtxTRrbg6ijGEiG5cCQuObspn0UmSgbeKYng3Q0IyjSANRG1FdvvUAVk6WRHXFMloljEh3NGDJsIXnhAbiQDI2a5YvdHaA5plHkKZIXHoDLaGOT5rgmjskiD5DmmEKRNcDZUc%2FloC%2FCI5rlm6f7h5rjbmAJ0C%2F6tnqtBlipdUyOeqJIL2GaYwrwKDGtdF4Id0me%2B7r6K81yB8K8uFtyUESYKnmWRzVBZAHSLNcirAT6RDVHhGZLgZ90%2FoLmmAM8EKgfFy1kGC%2FreTKK4pEESEcxiAybKb3lkEZFlGukibUAWsfVKKtJ00r6%2Fw4jDJc8f%2FFd2HuA9Gr6c5QtwGW%2Ba8fsDVr5OH1po41txPfiYFR2coThspUjPov6%2F4k6ygLSHx6A86lmGW2sIP3hARhEP%2Bb7Lup1BdIco4F1vusaj4RPSZ6n%2FZXzRAfRh3N4DuGjvmqaSOyihsG%2B3lT2dwk7l5kWnlS4lMN82VcxLyuQjqUvzfwV5SIf9UzkXqWGS3ysQn5WoGY%2Bb%2BFJlYs5xM0%2BCvkJkPIVL3VMfIQZfso40jquQMPcMmocCYMlz%2FMuJdxXoKKfpdAEcaNrAfcACdc61zBhqPtj53QJ05GcTxWvudYxwSgt1MpmXu9tAbcVqJp6LDxpJvQh51LALUBFrnAab8ITLncZ7hagTCSfezJxUrfH0C1AyqVO400SBAwQvN9xvAnvXJfBrgGqcRxvwjvLZbAFyAQNUKvjeBOe02PoGqDDjuNNeIdcBrsG6C3H8SY8p42rXAP0D8fxJjTl7y7D3QIkvOQ03iTBLpfBrivQC47jTWgZtw8bur4SXXAab5Ig7zLY7XYOEHIcwF6RTqt%2FUeA8gWJvCzitQFLa8HGVSw0T1GqX8ICfW1ofc65hwlCWuZZwD9DbrAXecK5j4naQf%2FOEaxHnAMlWjiH81LWOid3PZSctrkV8fS5sIXDUSy0Th2NU%2Bfmh9xIgKXAA4WEftUwMhF9JI6%2F6KOVvc4UM38feG0uDo%2B2PlRfeAiSN%2FBPlh77qmYgo83ytPuB7g6nS%2BRdbgKE%2B6xpvXqaVIbLJ3%2FNVr1vcSSOtlI4xCHqCjOmSkmGGz%2FBABHskSoEtCD%2FwXdc4e0jWs8530Wi2%2BYUMOZ4Eroqivumx56lieBSHsESy77FAkSKfA%2FZEUd%2F0yEGEiVGd4BPZxtmygX0UGUvpDFATRgsZJkmel6OaINKd12UDO8kwAdxfMjc9psD0KJ73dBb51v2ynnUIM6Oex7zLt6TA0qgnieXsB8nzCPh79dOchvALKXBvPFPFSLPciXR9lJLx5mEK3OJ6o1h3xXr6jDTxI0qnNJto%2FIwCM%2BIKD4Q6tTnLzPZTjm13M1%2BUedLE3LinDXL%2BlTSxCGEWMf6klDXhnhDhKU0dkGb5DMJS4D0h%2B0ixNoTbJM%2FCUA0Ev4RoliEIfwQuDt1LyhwCPisF%2FhSyieABAtARXEQ1f8BuA%2BkeYS%2BtjJeNbA%2FdSiLOAJVN7KWFeoTVoXtJgc1kGJaE8EBCVqAOCkKWryPcS0LCnTBLaPV%2FT4%2BLRAWog%2BYYBywBzgndS0K8A8ySQvI%2BuJDIAAFoPZfQRgMwOHQvge0BrpcCW0I30pXEXiakkVfox0hKK1GlWkMfhiY1PJDgFagzzXITwkIqZ1fYVoR7yPO9ON%2BW6I1UBAhARzGQDI9R%2Fv%2FV340wVfJsDN1IdyT2EnYi2cBL1DACYT6lm6XKUQNVfCwt4YEUrUCdaR3XofyS8tnY6ijCXZLnodCN9FQqAwSgdXyIIo8ibuddJcBOqpgijewI3UhvpOYSdiLJs4daxiB8l%2FR%2BkHEJRxie1vBAilegzrSOq1CWABeG7qWbDgLTpcDK0I24KosAAWg9H6CNxcC40L2ckvAMMFXybht8J0XZBAja30urYzbK%2FUCf0P2coIiwgGbmylaOhW7Gl7IKUAcdxTAyLAMGhO4FAOV1Mtwkefc9CZMmtU%2BiT0U28Cx9uRL4XehegDVUc3k5hgfKdAXq0OmS9mPgjNinF%2B4nzzeS%2FnaEi7IOUAetow5lOXBBTFMeRJkmTayJab5gKiJAcPy22RXAiEgnEp6lletlI7sjnSchyvI5UFdkE3upYQxE%2BnnxBpoZXSnhgQpagTq0Py%2F6Nsrd%2BPz%2Bhfnkub2cn%2B90peIC1EHrmIyyGDjTsVQLMEMKLHZuKoUqNkBw%2FC2Q3wP9e1miGeE6yfO0z77SpKIDBKBZsgir6Pn56UcQPl3J4YEKehJ9MtJEEzCWnh1%2F3UyG8ZUeHrAV6DgdTY4iqzn95ewwytj24FW8il%2BBOsh6Cgg3cOp7i9qAaRae%2F7EAdSJ5VgFfO%2Bk%2FUO4oh3t4fLJLWBc0SwPChBO%2B%2FLgUmBSkoQSzFagr1UwH9h3%2Fs7CXvnwpXEPJZQHqgjTyJsqcTl%2BaLWvtLDTTQ5qjUXM8FbqPJKsO3UCiKd9ByvZDjMYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYYyrQfwEGQyJFQbtWewAAAABJRU5ErkJggg%3D%3D" referrerpolicy="no-referrer"></td></tr><tr><td style='text-align:center;' >充钱就能变得更强</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/你在想-Peach!-red?colorA=43AD8D&amp;logo=Tencent-QQ" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >最大的同性交流网站</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/%E6%B2%A1%E9%94%99-%E5%B0%B1%E6%98%AF%E6%88%91-lightgrey?logo=Github" referrerpolicy="no-referrer"></a></td></tr></tbody>
</table>





