---
layout: post
title: 如何放置多个 MIT 协议声明文件
category: 技术
tags:  tech,programming
keywords: license,MIT,open source
---

<blockquote> <p>大部分关于开源协议的帖子都着重讲了几个主流的开源协议是什么，但是我们常遇到如何合理放置多个开源协议文件的问题。这里介绍一个简单合理的方法。</p> </blockquote>

## 关于开源协议

这个博客的源码基于几个公开的博客组件极其源码，具体
我在博客首页以及源码的 [Github Repository](https://github.com/bianandrew/bianandrew.github.io) 中有说明。

我很喜欢自己搭建博客平台的方式， 以后也会继续改进
现有的博客主题。 我喜欢开源精神，所以也把博客的源代码公开。但是我一开始并不清楚如何选一个合适的开源协议 (license)。

经过一番查找，我发现一些关于开源协议的帖子，比如：
[认识各种开源协议及其关系](http://blog.jasonding.top/2015/05/11/Git/%E3%80%90Git%E3%80%91%E8%AE%A4%E8%AF%86%E5%90%84%E7%A7%8D%E5%BC%80%E6%BA%90%E5%8D%8F%E8%AE%AE%E5%8F%8A%E5%85%B6%E5%85%B3%E7%B3%BB/),
[如何选择开源许可证?](http://www.ruanyifeng.com/blog/2011/05/how_to_choose_free_software_licenses.html),
[开源软件许可协议简介](http://www.vaikan.com/a-short-guide-to-open-source-and-similar-licenses/),
[狗日的开源软件许可证](http://coolshell.cn/articles/4657.html)。

我最终决定使用比较宽松的 MIT 协议，这也是此博客基于的源码之一 [Su Yan](https://github.com/suyan/suyan.github.io) 博客使用的协议。为了方便，咱们把基于的源码称为“上家”， 后续的使用者称为“下家”。

## 怎么放置多个声明？

[MIT协议](https://opensource.org/licenses/MIT)的内容十分简单，具体可见链接，不再罗列。它要求下家必须_原样_保留上家的协议声明文件。但是问题来了，
<blockquote> <p>根据 MIT 协议，我的源码必须包含上家的 MIT 协议声明文件，我也要放置自己的协议声明。 而且不同的协议声明文件名字都相同（基本都是 LICENSE），该怎么合理放置它们呢？</p> </blockquote>

我发现了一个帖子 [How to handle multiple licenses in your code](http://softwareengineering.stackexchange.com/questions/218490/how-to-handle-multiple-licenses-in-your-code), 从中得到一个合理的解决办法。

- 将自己的协议声明文件 (LICENSE) 放在根目录 ./
- 将其他上家的声明文件统一放在一个子目录，比如 ./3rd_party_licenses/  
- 依照不同上家的名字继续建立子目录，然后将其声明文件放入。比如我把 [Su Yan](https://github.com/suyan/suyan.github.io) 的声明文件放在 ./3rd_party_licenses/SU_YAN/ 子目录下。
- 在 README 中清楚说明使用了哪些上家的源码，以及他们的声明文件的具体位置。 
