---
layout: page
title: "Podcasting With Jekyll & follow.is"
permalink: /podcast
---

当前页面基于 [Jekyll](https://jekyllrb.com/) 自动生成, 
音频文件用 [七牛云](https://www.qiniu.com/) 发布,
而网站整体基于 [GitHub pages](https://pages.github.com/) 发布.

### Why?
> Why not?

The simple answer is that podcasting relies on a pretty simple technology - RSS. RSS often gets generated for a website almost as a by-product of adding content, this allows people to "subscribe" to your website and be notified or fed updates. Jekyll generates RSS straight out of the box and every podcast needs a website so we thought - why not kill two birds with one stone?

### How?
> 参考: [Podcasting With Jekyll](https://wiobyrne.github.io/infusing-computing-pod/podcast)


思路很简单:

- Podcasting 只是一个可以用 RSS 自动检索内容变化的网站
- 而 GitHub-pages 内置了高效 [SSG](https://about.gitlab.com/blog/2016/06/03/ssg-overview-gitlab-pages-part-1-dynamic-x-static/) 服务
- 那么, 嘦解决音频文件的发布
- 网站/RSS 的生成, 就都可以交给 GitHub 自动完成
- 幸好, 这个自动完成就是 [Jekyll](https://jekyllrb.com/)
- 更加幸运的是, 早已有好人按照这个思路完成, 并分享了如何配置
- 那就照猫画虎就好 ;-)

### 过程

**1.** 录制交流为 .mp3 或其它有效格式

**2.** 根据情况进行后期编辑, 也可以不处理(如果听众能忍的话)

**3.** 增补对应 Podcasting 需要的 metadata

**4.** 发布音频到 CDN 空间, 并获得链接

**5.** 配置好网站模板, 增补必须的信息到 YAML 节点中

``` yaml
layout: post
title: "Title Goes Here"
date: Publishing date and time
file: link to file in S3
summary: "Quick exerpt of episode"
description: "Longer information"
duration: "how long in minutes and seconds" 
length: "in seconds"
explicit: "do we swear" 
keywords: "keyword tags"
block: "hold back publishing it" 
voices: "who did the talking"
```

**6.** 将相关链接和说明增补到对应声明中. 

**7.** 将所有 push 给 GitHub

**8.** 新节目将自动化更新到网站以及 RSS 


### 能复用嘛?
> 当然:

最简洁的方式:

- clone [101camp/fm: FM\.101\.camp 蟒营™播客](https://github.com/101camp/fm) 
- 然后, 根据自己的情况对应修改
- 测试, 检验是否吻合自己的设计
- 就可以愉快的发布自己的 播客网站了


当然, 如果对样式不满意, 随时可以对 CSS 以及模板进行对应增补,

有任何问题, 欢迎随时交流:

- 邮件 -> ask(AT)101.camp
- 列表 -> 101camp@googlegroups.com
- 频道 -> 101camp.slack.com #general 

Cheers!


## upgrade
> 241015 尝试进入 follow.is

这是一个全新的 RSS 使用平台/工具, 也是一个全新的 web3 赛道,
先看看如何可以帮助进行高效的内容分发吧;

加入也很简单:

- 将 RSS 订阅
- 然后, 选择认证
    + 也就是在 `_config.yml` 追加官方要求的内容:
    + `feedId:58858970875044864+userId:68573755406424064`







