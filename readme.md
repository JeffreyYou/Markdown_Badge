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

<div align=center><img src="https://img.shields.io/badge/I%20love%20you%20-three%20thound-yellow?colorA=green&logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAAMp0lEQVR4nO2be3TV1ZXHP%2Bd3kxCSEN6PBALm%2FYIBRQJBmIQQ0ECpCoRHbUc6tjrV2lntdIHSSruKD8AuddXptM44otUZoIGCQgxggsEAgihiSMIjz%2FJIiICQFwk33Hvmj1%2FuzX2c3829NwH%2FGL5rZeWcs89vn7337%2FzO2WeffeEO7uD%2FNcStHiAzc0VwUEhzmhXTdJAJQpBoRUYKxEAgrKtbq0Q2aYh6KTkN4oww8WlnS%2BiR4uK3O26lfLfEANnZuQPpZ10E2nKQM4BgP1l1gDgA1k03Ay1%2FK96x41pfygl9bIC5CxYlWS1iJYLl%2BK%2B0EToEbJGY1hfmbznZV0z7xABzF%2BRGS6vcIGEhoLnSx40dwz%2BMTyEm%2Bi7GREYwatQIwkJDCQ7WbdTR0UFLayuNjZc4X99AdU0dpWXlnD13QTWcFSG2I60rC%2FO31fRW9l4ZICcnp59ZC10p4FmgvyMtIT6W7Fn%2FSMaMdIYMGewX%2FyvfXGV%2FySEKP%2F6Eyio3XTuQrAuUbesKCgpu%2BKdBLwyQNW%2FhOE0zbUbKaXZmQjB1yj0sX7KQlKQEf1krUVVdy7b3d7Gv%2BABWq7WbIPhSIJd%2BtGtbpT98%2FTLAnO%2FkPiylfBsIt7UlJcbzs5%2F8iPi4GH9Yeo3TlVW8%2Fh%2F%2FzenKKsfmFmBFYf7Wv%2FnKz2cDZM%2FP%2FQnI1wETQL%2BgIJ740aN8J2cOQtzyXRUAKSUf5O%2FhP9%2F6C2Zzp63ZCuKnhfl5f%2FKFl8mXznPmL14NvELXQjc2ajTr1j7H1Cn33DblQf%2FUkhLiSJ96L1%2BVltHc3AL6y5wfm5DSWVNZUeI1L287zp63%2BAkh%2BLOtnpyUwPO%2FeYbwAQN6flhKqDwL5TVQfR4aLsE3zdDRtXYF94MhAyFiGMRFQWqM%2Ft8Lo7a2tbFm7QZOlFU4Nv%2BsMH%2Fr697o5ZUBsucvXgj8la4ZMy3tXp575hcEBQV6fvBKE%2Bw%2BBAe%2B1Mu%2BYOggmDkJHpiuG8cDzOZO1q57hcOffW5rsiBZVPjh1vd7GqZHA2TlLI3VNMsxuha8CeNTWPe7X3tWvqUNNu%2BBjz%2BHm5aehvCMABNkTYGl98OAEMNuZnMnzzy3lhPldh%2BpSdPE3Xt35tV6Yu9xDcjNzQ26cdNaAESD%2Fs1veGEN%2Fft7cPIOHocXN8KpOrBKT%2By9g1Xqn82%2BozB8MESNUnYzmUzcl57GocOf2daEYCTpg8NnvNPQ8IVV%2BRA9GCAiOmW1gEdAX%2B3XrX2OkSOGqztbLPBf22HTHuhemfsO5k44fAKutcKkRNDcJ29QUBDjU5LZW1SMxWIFGB08oL299kzFASO2hgbImrdwnCbEJiAQ4MnHf8i0tMnqzjc64ffvwqGvfFPKH9Sch7p6mJKqfx4uGDJ4ECH9%2B3P0i%2BMACJg6Ni7p3bqqk80qdm5%2BezdBrAdCAJIS4lgwb666o8UCr7wHX57yWRe%2F8cVJePU9sKhn9kMLcoiPtTtkYSZNe8mIldIAs%2BctTUCIXND33Kf%2B5THjff7NHbdXeRuOnYK3dihJusz%2FbJdZwPLs%2BYuULqrSAJq4udJGm5Y2maSEOLUQn5ZC0Wc%2By95n%2BOgIHDiuJKUmJzJl8t22qgnEv6n6uRkgJ%2BeRcIl4xFZfsuhB9eAt1%2BHN7T5KfAvw1vv6tqvAssVOsj86d%2B4PQl37uBngpjAvpCuYERtzF%2BNTktQDb9qtG%2BHbRut12LJXSZowPoXYmLts1VBLYPsC1z5uBpCCZbZyVsZM9aBXmqD4czXt20DRUbisjpbNyphhLwu6dbPByQA5OTn9QGbY6hkz09UD7j7Yew%2BvL2GxwJ5PlaTMmdMdq7MyMzMDHBucKmYtNE10Tf%2FIiFFqp0dKw4VHidD%2BkDEZoiN1o52q0%2F2FzpvO%2FQIDYMbdkDgOTJru%2FX1yDK57GRT%2B5Bh87wG3A9TIEcOJjBhFfcNFgPDAkKGTAPv0dTKABtNtzuuE1GT1QGfOen%2BwSY2FX3zf2YefnQYLs%2BDlv8D5Rr0taiSsXAEjh3T3y5gMi7P1%2Fb7ci9Df1WaoOgfxY91IEyek2AwAmnYfDgZw%2BgSsSPuKZxjZqajuWRiAyOGwaoX6ABMxDH77BIyL0P9%2B84Sz8jaEh8KqH%2Bq8vEGF%2BtwT1%2B0UIaU10ZHmMgNEgm0GjI5UHzqoOu%2BdMLnZEBxkTA8PhTU%2F1ssD3HanbgQH6TPhD5t6HrPqnLJ5dGSEQ02Ld6Q5GUDCGFt55IgR6kEaLvcsCMBEL4KinhT3lRfARbVsEaNGdleEjHKkuW6D9vBOWJiBcFeVZwpnCAGejsy%2BIiTYq%2BgQ36jXprAwh89Q4hTCcjWA7a6O%2FsEGCnSYexZESsO34RcuXtF59oR29fVASH%2BnKwuPBrBD0stgxr6jvXveEd46Xd4FZp0UczVAq63Q3m6w%2F3pa2Bzx4UE4UdVzv55wug4%2BNIxnOMNAtuvt7Y7VVseKqwFabIW2NgM%2Ff3C4ut0VFgtseBvKvdw2Vai9AOvfcXeajGAQPG1tddBFdOsIbgYQ9n3kYuPX6kEihnknDOiRonUb%2FTNC7QVY%2B6Z%2B2PEWo9SyNVxstJeF5KwjzckAEqv9fu1CfYN6kLgodbsR%2FDGCP8oDxKtlc9RFIp2%2BS825Iuyhnapqg2hyqh93f74YwV%2FlAVLUsjneLEuJU%2FjKxRXmkK18otzppqUb8WNhqOeLCiW8MUJvlB86CGLHKEmlZeX2skloBx1pTgYIsrZ9BrQD1Dc00vj1JXduQuinNn%2FgyQi9UR70WyTFNtjYeIn6Bvsa0DwwBKejrJMBuhIN9tvqxSWHUCJnujIk7RVURuit8oEBkHOfklRc0v3CJRTl5eU5BTLcI0LIzbbyvmKD%2FXfIQJg1xT9hQTfCSxvhnV3w3oew5s%2F%2BKw%2F61ZnB9rxvv8OMF2KLK93NAEHW4O10fQY1tXWOd23OWH6%2F94cZFcydkF8CH%2ByHG16410YIC4Elc5Sk0rIKamrrbNXWENGx07WPmwEKCv6nGeS7tvpftxlcsIaFwI8f9kPiPsZjDxq%2BiM15TlHrjTt37nSbZsqzgBD8HrAAHDl6jJOnzqgHnzYB5kxT024H7k%2BH%2ByYpSWUVp%2Fj8mP2q7qamiVdV%2FZQG%2BGjXtkoBeaCno%2FzxjY1Io9PYYw9C2ngfJe8D3JMEK76rJFmtVv74xlvdMkv%2B1%2Bia3Pg0qIlVwHXQE5M%2ByN%2Bj7qhp8PQyXaDbhcnJ8PPv68FTBXbsLHB05FqtmlhtxMpwL6s5U9EUE5%2BiIcgCOF5aRvrUexk8aJB75wATpE%2BE5laoUSY39h3uT4cnl%2BhbnwJV1bW8sOE1eyqdgDVF%2BVsLjNh53MwnT0o93GEWDyAYbbFY%2Baq0nNmZMwkKUhw7NaG%2FmdEjoKy673MEBoTAU0vguxnK3ACAlpZWnl3zAteauiJDQhy%2BenHI434nSFRUVFhiEpKLQKwAgpubWygtqyArYwYBAeo3QNQoyErTE6D%2B3tD7LJHAAJgzFX75T4auLsANs5lf%2FfZFqmvs2941TRNzDxS%2Fe8UT%2Bx7duZrKk1ejk5JPCSlyAe3y5SvU1J1lRvpUTCaDx%2FsFwj3JMOteMJn0ayujAIsRhg2CudPgX5fD9IngISfphtnM8%2Bte5djxUluTRRNy2d5dW4%2F0NIzXaXLZ83MfB%2FmGrZ6clMDaNc8wMNzLNLmqc3rcvuqcHi%2B80qTH8AR6mtzQgfp5Pj5KP9XFjvEuTa61jTVr1zs7bEI8Xbgr79%2B90cun7MY58xevlvCCrR41JpJfr%2Fo5MdF3eXrslqGqupbn17%2FqfN4XrC7atdUwI8QVPp1oaiorSqITUi4JyAFEc3MLe4uKCQsNJTE%2B9ramyu7YWcCLL7%2FGtWv2ULhFCPlU4a5tr%2FnCyy%2BJs%2BctWoQQG3EIMSfGx%2FH0k4%2BRGG%2BQTdJHOHW6kj%2F86U3X9PkmJI96kxjpCr9f2ex5SxOEsGwB7L6oLV1%2BWe7DpCYnenjad1RW17A5bwclBw%2B7eKXimMnE0j0f5PkVgu7VnM3MXBFsCm15ViBW4vITmfjYGLJmzSRjRjrDhw31i%2F%2Bly1fYX3KIouISVYiuHcmLgbLt5W%2FlBxOO6Eqn3QA8hMK9HjM6gokTUomNiWbM6AhGDB%2FGwPBwgoP7AdDRcYOm5mYav77EhfqLVFXX8tWJcqPArBXYGmAJWLV79%2BY6VQdf0Ker1uyc3BQh5CoES7gFP5pCssliFes%2F3p13uq%2BY3pJlO%2FOhhwYFdJoW9sHP5tqRlAjEJmlme2Fhno8p5z3jtvxwMnBA21SrlNOFlXiESAAZCQzC4YeTwDUQ9Uh5BsQZDcshk2w%2F0pvv%2Bw7u4A56xP8By7RQqkt4MZIAAAAASUVORK5CYII%3D"></img></div>

<div align=center><img src="https://img.shields.io/badge/I%20love%20you%20-three%20thound-red?logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAJAAAACQCAYAAADnRuK4AAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAAJMUlEQVR4nO3df5CVVR3H8ff37goSq6WluWr1B440ohBJNMC9y2IzKgM5E4gQklbUYCSIDuVYjf3UzIZRCeiHY9GAI4TbRD%2BAUZTl3gWEkQETTNF%2BMAioRGmwoMvu%2FfbH3aUNF9jdc57nPM%2B939cMw7Bwvue7cz97nsu9zz0HjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGpImEbuBk9JOczRnUIQxGGIgyEDgPeB%2FQn1Lvb7b%2FegvYjbKdDNtQtkmB%2FeG6fzfNUYswlCJDEYYCH6b0vby3%2FXcFmil9PweAF4FdwHO0UJDN%2FCdQ66eUqADpSAZQxY3AOOBKoKr3xdiB8FugQQr82VOLPWshyxCECcBEYJBDqVZgK7AKZak08TcvDXoQPEA6iSr2cwPCV4GRkfSkvAg8wFn8Wlbzjvf6naeq50yK3IxyOzAwiimAjSgLqeU3soK2CObotmAB0nqqaeMLwJ3AgJim3Q88SD8WyhM0%2ByysV9OfI9yKMAe4wGftU3gF4T4%2ByOJQQQoSIB3FMDIsAj4RYn6EvSi3SYEGH%2BU0y3iEBcBHfNTrMWE7yq1SYEP8U8dIR9CPauYBt8Q990k8ThWzpJHXejNYc9SiLGh%2FnhOaoiyimrnSyNtxTRrbg6ijGEiG5cCQuObspn0UmSgbeKYng3Q0IyjSANRG1FdvvUAVk6WRHXFMloljEh3NGDJsIXnhAbiQDI2a5YvdHaA5plHkKZIXHoDLaGOT5rgmjskiD5DmmEKRNcDZUc%2FloC%2FCI5rlm6f7h5rjbmAJ0C%2F6tnqtBlipdUyOeqJIL2GaYwrwKDGtdF4Id0me%2B7r6K81yB8K8uFtyUESYKnmWRzVBZAHSLNcirAT6RDVHhGZLgZ90%2FoLmmAM8EKgfFy1kGC%2FreTKK4pEESEcxiAybKb3lkEZFlGukibUAWsfVKKtJ00r6%2Fw4jDJc8f%2FFd2HuA9Gr6c5QtwGW%2Ba8fsDVr5OH1po41txPfiYFR2coThspUjPov6%2F4k6ygLSHx6A86lmGW2sIP3hARhEP%2Bb7Lup1BdIco4F1vusaj4RPSZ6n%2FZXzRAfRh3N4DuGjvmqaSOyihsG%2B3lT2dwk7l5kWnlS4lMN82VcxLyuQjqUvzfwV5SIf9UzkXqWGS3ysQn5WoGY%2Bb%2BFJlYs5xM0%2BCvkJkPIVL3VMfIQZfso40jquQMPcMmocCYMlz%2FMuJdxXoKKfpdAEcaNrAfcACdc61zBhqPtj53QJ05GcTxWvudYxwSgt1MpmXu9tAbcVqJp6LDxpJvQh51LALUBFrnAab8ITLncZ7hagTCSfezJxUrfH0C1AyqVO400SBAwQvN9xvAnvXJfBrgGqcRxvwjvLZbAFyAQNUKvjeBOe02PoGqDDjuNNeIdcBrsG6C3H8SY8p42rXAP0D8fxJjTl7y7D3QIkvOQ03iTBLpfBrivQC47jTWgZtw8bur4SXXAab5Ig7zLY7XYOEHIcwF6RTqt%2FUeA8gWJvCzitQFLa8HGVSw0T1GqX8ICfW1ofc65hwlCWuZZwD9DbrAXecK5j4naQf%2FOEaxHnAMlWjiH81LWOid3PZSctrkV8fS5sIXDUSy0Th2NU%2Bfmh9xIgKXAA4WEftUwMhF9JI6%2F6KOVvc4UM38feG0uDo%2B2PlRfeAiSN%2FBPlh77qmYgo83ytPuB7g6nS%2BRdbgKE%2B6xpvXqaVIbLJ3%2FNVr1vcSSOtlI4xCHqCjOmSkmGGz%2FBABHskSoEtCD%2FwXdc4e0jWs8530Wi2%2BYUMOZ4Eroqivumx56lieBSHsESy77FAkSKfA%2FZEUd%2F0yEGEiVGd4BPZxtmygX0UGUvpDFATRgsZJkmel6OaINKd12UDO8kwAdxfMjc9psD0KJ73dBb51v2ynnUIM6Oex7zLt6TA0qgnieXsB8nzCPh79dOchvALKXBvPFPFSLPciXR9lJLx5mEK3OJ6o1h3xXr6jDTxI0qnNJto%2FIwCM%2BIKD4Q6tTnLzPZTjm13M1%2BUedLE3LinDXL%2BlTSxCGEWMf6klDXhnhDhKU0dkGb5DMJS4D0h%2B0ixNoTbJM%2FCUA0Ev4RoliEIfwQuDt1LyhwCPisF%2FhSyieABAtARXEQ1f8BuA%2BkeYS%2BtjJeNbA%2FdSiLOAJVN7KWFeoTVoXtJgc1kGJaE8EBCVqAOCkKWryPcS0LCnTBLaPV%2FT4%2BLRAWog%2BYYBywBzgndS0K8A8ySQvI%2BuJDIAAFoPZfQRgMwOHQvge0BrpcCW0I30pXEXiakkVfox0hKK1GlWkMfhiY1PJDgFagzzXITwkIqZ1fYVoR7yPO9ON%2BW6I1UBAhARzGQDI9R%2Fv%2FV340wVfJsDN1IdyT2EnYi2cBL1DACYT6lm6XKUQNVfCwt4YEUrUCdaR3XofyS8tnY6ijCXZLnodCN9FQqAwSgdXyIIo8ibuddJcBOqpgijewI3UhvpOYSdiLJs4daxiB8l%2FR%2BkHEJRxie1vBAilegzrSOq1CWABeG7qWbDgLTpcDK0I24KosAAWg9H6CNxcC40L2ckvAMMFXybht8J0XZBAja30urYzbK%2FUCf0P2coIiwgGbmylaOhW7Gl7IKUAcdxTAyLAMGhO4FAOV1Mtwkefc9CZMmtU%2BiT0U28Cx9uRL4XehegDVUc3k5hgfKdAXq0OmS9mPgjNinF%2B4nzzeS%2FnaEi7IOUAetow5lOXBBTFMeRJkmTayJab5gKiJAcPy22RXAiEgnEp6lletlI7sjnSchyvI5UFdkE3upYQxE%2BnnxBpoZXSnhgQpagTq0Py%2F6Nsrd%2BPz%2Bhfnkub2cn%2B90peIC1EHrmIyyGDjTsVQLMEMKLHZuKoUqNkBw%2FC2Q3wP9e1miGeE6yfO0z77SpKIDBKBZsgir6Pn56UcQPl3J4YEKehJ9MtJEEzCWnh1%2F3UyG8ZUeHrAV6DgdTY4iqzn95ewwytj24FW8il%2BBOsh6Cgg3cOp7i9qAaRae%2F7EAdSJ5VgFfO%2Bk%2FUO4oh3t4fLJLWBc0SwPChBO%2B%2FLgUmBSkoQSzFagr1UwH9h3%2Fs7CXvnwpXEPJZQHqgjTyJsqcTl%2BaLWvtLDTTQ5qjUXM8FbqPJKsO3UCiKd9ByvZDjMYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYYyrQfwEGQyJFQbtWewAAAABJRU5ErkJggg%3D%3D"></img></div>

<div align=center><img src="https://img.shields.io/badge/I%20love%20you%20-three%20thound-red?colorB=orange&colorA=43AD8D&logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8%2F9hAAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAABkUlEQVQ4ja2Sv0tbURTHv%2Fe%2Be5%2F68kIgi2gWETu5CHXrGAiNEezaQRBdBdHB%2Fgc6Cf4DIdBFKHQITdI8p0IlIJTi0i4BURDX5JH7ou%2B9%2B8MlYkxJiMXPdDjf8zmHCxd4TUyxmDSl0uTQvFSaNMVisr9HACCu1d4R1z2gtr0MrSMt5W8IccxWVr4BgPS8D3CcHcr5EozhOorOtRCf7ELhFzGelzCue0EcZ%2BHZNSm70vd3oZTF0ukjwthUf66D4A9tNpdZbFlbfEAGAMKYw5LJw149NZjTRGIxzmQ2GGFsbtibiW2nh2W9%2FA1FGIajhkYSxxFFHNeMlPcvlrVWpNs9o3x19afudE5e6qtO5ztbW6tSALCur%2FeUEGfjyiaKLpUQ%2B0DvHwDAfaUyz1OpL9R1346Uw%2FBGtVrrPJ%2F%2F8WwBAASnp7MTnH%2B2UqksCPlH1kHwV%2Fn%2Bpl0onD%2F2aP9AIpe7tYD3st0%2BNEpFT6Y2qt3%2Beuf72X55JLJa%2FagbjaZuNK6ien17LGkQUS5PB%2FX6zH%2FJ4%2FIAd1%2BkpmPB%2FIUAAAAASUVORK5CYII%3D"></img></div>

### 8.自定义徽章展示

<table align=center>
<thead>
<tr><th style='text-align:center;' >展示</th><th style='text-align:center;' >效果</th></tr></thead>
<tbody><tr><td style='text-align:center;' >那个绿色的男人</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/G%E8%83%96%E8%BF%98%E6%88%91-%E8%A1%80%E6%B1%97%E9%92%B1%EF%BC%81-yellow?colorA=4a9718&amp;logo=steam" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >求求了给个三连吧</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/下次-一定-orgreen?logoColor=white&amp;logo=Bilibili" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >I love open source</td><td style='text-align:center;' ><img src="https://img.shields.io/badge/I%20love-Open%20Soucre-43AD8D?logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAJAAAACQCAYAAADnRuK4AAAABmJLR0QA%2FwD%2FAP%2BgvaeTAAAJMUlEQVR4nO3df5CVVR3H8ff37goSq6WluWr1B440ohBJNMC9y2IzKgM5E4gQklbUYCSIDuVYjf3UzIZRCeiHY9GAI4TbRD%2BAUZTl3gWEkQETTNF%2BMAioRGmwoMvu%2FfbH3aUNF9jdc57nPM%2B939cMw7Bwvue7cz97nsu9zz0HjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGpImEbuBk9JOczRnUIQxGGIgyEDgPeB%2FQn1Lvb7b%2FegvYjbKdDNtQtkmB%2FeG6fzfNUYswlCJDEYYCH6b0vby3%2FXcFmil9PweAF4FdwHO0UJDN%2FCdQ66eUqADpSAZQxY3AOOBKoKr3xdiB8FugQQr82VOLPWshyxCECcBEYJBDqVZgK7AKZak08TcvDXoQPEA6iSr2cwPCV4GRkfSkvAg8wFn8Wlbzjvf6naeq50yK3IxyOzAwiimAjSgLqeU3soK2CObotmAB0nqqaeMLwJ3AgJim3Q88SD8WyhM0%2ByysV9OfI9yKMAe4wGftU3gF4T4%2ByOJQQQoSIB3FMDIsAj4RYn6EvSi3SYEGH%2BU0y3iEBcBHfNTrMWE7yq1SYEP8U8dIR9CPauYBt8Q990k8ThWzpJHXejNYc9SiLGh%2FnhOaoiyimrnSyNtxTRrbg6ijGEiG5cCQuObspn0UmSgbeKYng3Q0IyjSANRG1FdvvUAVk6WRHXFMloljEh3NGDJsIXnhAbiQDI2a5YvdHaA5plHkKZIXHoDLaGOT5rgmjskiD5DmmEKRNcDZUc%2FloC%2FCI5rlm6f7h5rjbmAJ0C%2F6tnqtBlipdUyOeqJIL2GaYwrwKDGtdF4Id0me%2B7r6K81yB8K8uFtyUESYKnmWRzVBZAHSLNcirAT6RDVHhGZLgZ90%2FoLmmAM8EKgfFy1kGC%2FreTKK4pEESEcxiAybKb3lkEZFlGukibUAWsfVKKtJ00r6%2Fw4jDJc8f%2FFd2HuA9Gr6c5QtwGW%2Ba8fsDVr5OH1po41txPfiYFR2coThspUjPov6%2F4k6ygLSHx6A86lmGW2sIP3hARhEP%2Bb7Lup1BdIco4F1vusaj4RPSZ6n%2FZXzRAfRh3N4DuGjvmqaSOyihsG%2B3lT2dwk7l5kWnlS4lMN82VcxLyuQjqUvzfwV5SIf9UzkXqWGS3ysQn5WoGY%2Bb%2BFJlYs5xM0%2BCvkJkPIVL3VMfIQZfso40jquQMPcMmocCYMlz%2FMuJdxXoKKfpdAEcaNrAfcACdc61zBhqPtj53QJ05GcTxWvudYxwSgt1MpmXu9tAbcVqJp6LDxpJvQh51LALUBFrnAab8ITLncZ7hagTCSfezJxUrfH0C1AyqVO400SBAwQvN9xvAnvXJfBrgGqcRxvwjvLZbAFyAQNUKvjeBOe02PoGqDDjuNNeIdcBrsG6C3H8SY8p42rXAP0D8fxJjTl7y7D3QIkvOQ03iTBLpfBrivQC47jTWgZtw8bur4SXXAab5Ig7zLY7XYOEHIcwF6RTqt%2FUeA8gWJvCzitQFLa8HGVSw0T1GqX8ICfW1ofc65hwlCWuZZwD9DbrAXecK5j4naQf%2FOEaxHnAMlWjiH81LWOid3PZSctrkV8fS5sIXDUSy0Th2NU%2Bfmh9xIgKXAA4WEftUwMhF9JI6%2F6KOVvc4UM38feG0uDo%2B2PlRfeAiSN%2FBPlh77qmYgo83ytPuB7g6nS%2BRdbgKE%2B6xpvXqaVIbLJ3%2FNVr1vcSSOtlI4xCHqCjOmSkmGGz%2FBABHskSoEtCD%2FwXdc4e0jWs8530Wi2%2BYUMOZ4Eroqivumx56lieBSHsESy77FAkSKfA%2FZEUd%2F0yEGEiVGd4BPZxtmygX0UGUvpDFATRgsZJkmel6OaINKd12UDO8kwAdxfMjc9psD0KJ73dBb51v2ynnUIM6Oex7zLt6TA0qgnieXsB8nzCPh79dOchvALKXBvPFPFSLPciXR9lJLx5mEK3OJ6o1h3xXr6jDTxI0qnNJto%2FIwCM%2BIKD4Q6tTnLzPZTjm13M1%2BUedLE3LinDXL%2BlTSxCGEWMf6klDXhnhDhKU0dkGb5DMJS4D0h%2B0ixNoTbJM%2FCUA0Ev4RoliEIfwQuDt1LyhwCPisF%2FhSyieABAtARXEQ1f8BuA%2BkeYS%2BtjJeNbA%2FdSiLOAJVN7KWFeoTVoXtJgc1kGJaE8EBCVqAOCkKWryPcS0LCnTBLaPV%2FT4%2BLRAWog%2BYYBywBzgndS0K8A8ySQvI%2BuJDIAAFoPZfQRgMwOHQvge0BrpcCW0I30pXEXiakkVfox0hKK1GlWkMfhiY1PJDgFagzzXITwkIqZ1fYVoR7yPO9ON%2BW6I1UBAhARzGQDI9R%2Fv%2FV340wVfJsDN1IdyT2EnYi2cBL1DACYT6lm6XKUQNVfCwt4YEUrUCdaR3XofyS8tnY6ijCXZLnodCN9FQqAwSgdXyIIo8ibuddJcBOqpgijewI3UhvpOYSdiLJs4daxiB8l%2FR%2BkHEJRxie1vBAilegzrSOq1CWABeG7qWbDgLTpcDK0I24KosAAWg9H6CNxcC40L2ckvAMMFXybht8J0XZBAja30urYzbK%2FUCf0P2coIiwgGbmylaOhW7Gl7IKUAcdxTAyLAMGhO4FAOV1Mtwkefc9CZMmtU%2BiT0U28Cx9uRL4XehegDVUc3k5hgfKdAXq0OmS9mPgjNinF%2B4nzzeS%2FnaEi7IOUAetow5lOXBBTFMeRJkmTayJab5gKiJAcPy22RXAiEgnEp6lletlI7sjnSchyvI5UFdkE3upYQxE%2BnnxBpoZXSnhgQpagTq0Py%2F6Nsrd%2BPz%2Bhfnkub2cn%2B90peIC1EHrmIyyGDjTsVQLMEMKLHZuKoUqNkBw%2FC2Q3wP9e1miGeE6yfO0z77SpKIDBKBZsgir6Pn56UcQPl3J4YEKehJ9MtJEEzCWnh1%2F3UyG8ZUeHrAV6DgdTY4iqzn95ewwytj24FW8il%2BBOsh6Cgg3cOp7i9qAaRae%2F7EAdSJ5VgFfO%2Bk%2FUO4oh3t4fLJLWBc0SwPChBO%2B%2FLgUmBSkoQSzFagr1UwH9h3%2Fs7CXvnwpXEPJZQHqgjTyJsqcTl%2BaLWvtLDTTQ5qjUXM8FbqPJKsO3UCiKd9ByvZDjMYYY4wxxhhjjDHGGGOMMcYYY4wxxhhjjDHGGGOMMcYYYyrQfwEGQyJFQbtWewAAAABJRU5ErkJggg%3D%3D" referrerpolicy="no-referrer"></td></tr><tr><td style='text-align:center;' >充钱就能变得更强</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/你在想-Peach!-red?colorA=43AD8D&amp;logo=Tencent-QQ" referrerpolicy="no-referrer"></a></td></tr><tr><td style='text-align:center;' >最大的同性交流网站</td><td style='text-align:center;' ><a href='https://github.com/JeffreyYou/My_Documentation'><img src="https://img.shields.io/badge/%E6%B2%A1%E9%94%99-%E5%B0%B1%E6%98%AF%E6%88%91-lightgrey?logo=Github" referrerpolicy="no-referrer"></a></td></tr></tbody>
</table>





