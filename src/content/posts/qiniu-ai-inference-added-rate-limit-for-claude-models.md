---
title: 七牛AI大模型推理API为Claude系列模型添加了速率限制
published: 2026-05-18
description: ''
image: ''
tags: [AI,API]
category: '技术'
draft: false 
lang: ''
---
之前七牛云推理有一个拉新活动，可以白嫖Token
并且这个API其他人说 可以调用Claude 4.5 Sonnet 

但是好久都没用了，最近才发现该API模型添加了Rate Limit
并且是基于账号(UID)的每日Token限制(TPD)
![](https://bucket.002397.xyz/2026/05/53fb3bd94252e45e6e90c5c54b3d525f.jpg)

经后台查看数据，限制在 300k~400k Token间
![](https://bucket.002397.xyz/2026/05/c53c03006a94de6e94261d9442f3b45e.jpg)

之前是不限量调用，但现在限制这么死似乎也不能玩多少了

经论坛搜索，该限制早在72天前就被人发现
![](https://bucket.002397.xyz/2026/05/1cdeef14fe303e25c9487e2a1a73237c.png)