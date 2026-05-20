---
title: Beyond Compare 5 使用替换字符串进行破解
published: 2026-05-20
description: ''
image: ''
tags: [实用软件,工具]
category: '教程'
draft: false 
lang: ''
---
:::note
此教程是根据[这个消息](https://t.me/macked_channel/48)而写的\
`并非本人原创`，本人只是把完整操作重复了一遍做成手把手教程
:::

Beyond Compare 是一个极其实用的文件比对软件
![](https://static.efur.top/img/2026/05/a27122eadc43e286605ada42c52d67a8.png)

那我们该怎么进行破解呢？不妨试试用它自己来修改自己\
首先我们在官网下载[Beyond Compare 5 官方版](https://www.scootersoftware.com/download)（截止本文发布，最新版本为5.2.1）
![](https://static.efur.top/img/2026/05/21ad66c5263313e87ef3756ae402e294.png)

随后进行安装
![](https://static.efur.top/img/2026/05/aa5427851d86e467d267151d35676c46.png)
![](https://static.efur.top/img/2026/05/a6d650ce74423a09a3f4d61d0871e080.png)

此时我们会发现它会运行在评估模式中
![](https://static.efur.top/img/2026/05/ec5ba21632ce2983db4324f300c04d5d.png)

右键它，找到它的程序位置
![](https://static.efur.top/img/2026/05/a61f1fd3ea5a2020af1afe1a38ce0c68.png)

选中它，使用Ctrl+C和Ctrl+V迅速创建一个副本
![](https://static.efur.top/img/2026/05/9db442c0400778dbbc3e06af5ecb01d5.png)

返回刚刚安装的Beyond Compare，创建一个16进制比较的窗口
![](https://static.efur.top/img/2026/05/3684c5224f77d74833031386e4ae87be.png)

创建完成之后，把Beyond Compare的副本拖入进去
![](https://static.efur.top/img/2026/05/f49e1498e975a837adc06dda6ba7cdb9.png)

按下Ctrl+H 打开替换
![](https://static.efur.top/img/2026/05/78fb0e19f9ada7067cccfcc9e6929604.png)

随后把以下字符串粘贴到上面
```
7EFlNLs6Yqc3p-LtUOXBElimekQm8e3BTSeGhxhlpmVDeVVrrUAkLTXpZ7mK6jAPAOhyHiokPtYfmokklPELfOxt1s5HJmAnl-5r8YEvsQXY8-dm6EFwYJlXgWOCutNn2+FsvA7EXvM-2xZ1MW8LiGeYuXCA6Yt2wTuU4YWM+ZUBkIGEs1QRNRYIeGB9GB9YsS8U2-Z3uunZPgnA5pF+E8BRwYz9ZE--VFeKCPamspG7tdvjA3AJNRNrCVmJvwq5SqgEQwINdcmwwjmc4JetVK76og5A5sPOIXSwOjlYK+Sm8rvlJZoxh0XFfyioHz48JV3vXbBKjgAlPAc7Np1+wk
```
替换为以下字符串
```
oQmLWQCi9MaOxVy8P7sbCp0wEf5y8iyQTq+dKGEwbCWU5NdUo6zmOttrLH1IfqWaOqKhBz9qT4e6yY7n6Ew23D1FetT4op3p6mXemq00mJ06g30lfVQIRB4tA2vrzBa7m-VetHFZp0nq0fhyQNLh61BrqrnIIyRpmrN4J6xtp1vcDejne2UEVYUGiZIzERcVwhcfw05IfRNPQ8n6du5iyGqFsboU6iumCZ2wIj0SIr+IMvP9cvygLjOZc7Isr3tHmmBv6zHjixVgCwBuYkUwSrrjJ2p4zCQUm30E+66EOgRVOLvo75yUESv64x1tWs2XANrf3zj+ZB4kEmkAMKVVUU
```

![](https://static.efur.top/img/2026/05/7e5af80454ac25a069b9e1e8f7981c86.png)

按下Ctrl+S保存

随后将已经修好好的副本替换原版程序
![](https://static.efur.top/img/2026/05/46726c5c28b07712f8366c2972ab58bc.png)

再次打开Beyond Compare 会出现这个窗口
![](https://static.efur.top/img/2026/05/0e902a7d2ae99d4e2649b284e9bbca5a.png)
会要求我们输入许可证

输入以下许可证
```
--- BEGIN LICENSE KEY ---
5LfJhESgorpBtGn5GhUbWN5FS72aQZmgH7Hqo9uNcdxk18WjB4
ZZjBx6CLJ1HgSruyyCfc5b11k97J4Bt1ctcQZXHA7EmUZWQwhK
tpScrFuGYepCwQKSSZKfyQDTU1pHairJqVw7eXGfYurtMeatr9
xFZSiC3EoNCvkFksLSd5JUwqG3Gvn2hkywDSfF38pas6VeXiHj
m4UXmAwEMYgTbkys6JMYXPsjAhixHPVfRMBUeBDM5Uzutyf8om
BoGMk1Cd9tT1N1mxVfkgLc2mRJhhmGQh5M18J22FarkRnWSphy
iGQSeGUAASryXZjquSYz6FNpxJenbF9rAZ7WMaSBk1RkRsLkYh
--- END LICENSE KEY ---
```
![](https://static.efur.top/img/2026/05/d374527517040a434ee56dc5826d9fc2.png)
![](https://static.efur.top/img/2026/05/aa955a2e138eb0290dc93507caf7b3b1.png)

:::note
已知简体中文、英语的版本均可用此教程\
若无法下载到官方程序，这里有备份一份\
[5.2.1 法语 Windows](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/BCompare-fr-5.2.1.32035.exe) | [5.2.1 日语 Windows](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/BCompare-jp-5.2.1.32035.exe) | [5.2.1 简体中文 Windows](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/BCompare-zh-5.2.1.32035.exe) | [5.2.1 英语 Windows](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/BCompare-5.2.1.32035.exe) | [5.2.1 德语 Windows](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/BCompare-de-5.2.1.32035.exe) | [5.2.1 Linux RPM](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/bcompare-5.2.1.32035.x86_64.rpm) | [5.2.1 Linux DEB](https://res.efur.top/d/Guest/Beyond%20Compare%20Official/bcompare-5.2.1.32035_amd64.deb)
:::