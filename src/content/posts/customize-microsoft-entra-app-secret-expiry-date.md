---
title: 突破2年限制，让OneDrive挂载到OpenList不再轮换密钥
published: 2026-05-19
description: ''
image: ''
tags: [OneDrive,Microsoft]
category: '教程'
draft: false 
lang: ''
---

:::note
这个教程是`两个教程`串起来的\
分别是[主机贴士](https://zhujitips.com/3175)和[OpenList 文档](https://doc.oplist.org/guide/drivers/onedrive_app)
:::

## 0. 前言
之前早已在玩E5开发者OneDrive\
但之后被清退了\
之后M$又出现了空全局订阅E3的bug 导致现在E3 Dev又开始出现了一大批\
![](https://static.efur.top/img/2026/05/049bc961a8188aaf2333791dbcbd0a0d.png)
就是这个
反正也闲的没事做，就做一个手把手教程吧

## 1. 创建应用
使用`全局管理员`账号登录[Microsoft Entra(原AAD)控制台](https://entra.microsoft.com/#home)\
![](https://static.efur.top/img/2026/05/26aabb6c8652178f240bd5c72a1130ae.png)
![](https://static.efur.top/img/2026/05/e6154cf89037289f22defe3d55fcf33b.png)

左侧进行应用注册
![](https://static.efur.top/img/2026/05/df0f91e2d092792aefb87d1e19102a1a.png)
![](https://static.efur.top/img/2026/05/28351e84fe6b201af87a82943ac90c28.png)

此处按需填写 此处按[Openlist OneDriveAPP 文档](https://doc.oplist.org/guide/drivers/onedrive_app)为例

![](https://static.efur.top/img/2026/05/44066b926542092f80cd536507513cab.png)
![](https://static.efur.top/img/2026/05/d4b917722519eb8b89faa6755128900d.png)

此时我们获取了三个必要参数
![](https://static.efur.top/img/2026/05/83a0d19b6221555bdf2a8a315d0f8039.png)
其中\
对象ID是用于调用`Microsoft Graph API`进行创建应用密钥
租户ID和应用ID是用于授权OpenList使用

## 2. 授权API权限
事实上，[第二步](#2-授权api权限)和[第三步](#3-创建密钥)是可以不分先后的，这里只是为了获取密钥即可用的情况下先授权权限\
点开刚刚创建的应用 选择API权限 
默认只会有一个User.Read的权限
![](https://static.efur.top/img/2026/05/0f08778420ba31564625fc836eaedb35.png)

点开添加权限 按需添加权限（此处以[Openlist OneDriveAPP 文档](https://doc.oplist.org/guide/drivers/onedrive_app)为例）
![](https://static.efur.top/img/2026/05/deb8c1809bd2c51f80f187fdd43d7cb1.png)

更新权限之后 点按`代表 组织 授予管理员同意`
![](https://static.efur.top/img/2026/05/54a53fa94e73a2887293b890498f7f49.png)
![](https://static.efur.top/img/2026/05/42a45c5f03a4dcb4e07b9903e5337361.png)

若成功授予管理员权限，则应当变为如下图
![](https://static.efur.top/img/2026/05/b7f5d4dc97e80575c18e9632ff686502.png)
## 3. 创建密钥
按照 [Openlist OneDriveAPP 文档](https://doc.oplist.org/guide/drivers/onedrive_app) 来说，此时应该点按`证书和密码`，添加客户端密码\
但在Microsoft Entra中创建客户端密码是最长只有24个月 到时候还得轮换\
![](https://static.efur.top/img/2026/05/63895457816cd6da0e3bf2f9d5bf4750.png)

但根据[这个教程](https://zhujitips.com/3175)，我们可以知道透过Microsoft Graph API也可以创建客户端密码，并且可以`自定义到期时间`

那么直接开始吧！首先打开[Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)
打开就像这样
![](https://static.efur.top/img/2026/05/1c35d5e312a66437cd40faf1f4d6f922.png)

点击右上角 使用全局管理员账户登录
![](https://static.efur.top/img/2026/05/bf2fde1c1463362bbee3df7b2a0b50f2.png)
此时会有一个`请求征得的许可`，点击接受
![](https://static.efur.top/img/2026/05/7b4ccbeb7b5159a622847560806bf06e.png)

回到Graph Explorer，你应该可以看见你的组织租户名
![](https://static.efur.top/img/2026/05/10e8f5c875e5d7bee81508d9c3dd5665.png)

将请求方法改为POST，右边URL填入以下内容
```
https://graph.microsoft.com/v1.0/applications/{id}/addPassword
```
:::caution
此处请把你的 {id} 值替换为你实际的应用对象ID
:::
![](https://static.efur.top/img/2026/05/18ac01cbb6ca56c6e360ebd41736769a.png)

点击`修改权限`，进行授予权限
![](https://static.efur.top/img/2026/05/3cc4c1ebd4d6bd4c8125159c8932a534.png)
![](https://static.efur.top/img/2026/05/d83d8b51afb0898ad5034bbcca52aa9d.png)
![](https://static.efur.top/img/2026/05/071ec0abcdcbecf1565a0af1375b1451.png)

授予权限完成后，应该会是这样
![](https://static.efur.top/img/2026/05/5a77f965689e8561780884d29198fd09.png)

返回请求体，随后添加以下内容
![](https://static.efur.top/img/2026/05/3459600f9d08c35b18481bca64dc40e9.png)
```
{
    "passwordCredential": {
        "displayName": "OwO", 
        "endDateTime": "2333-03-03T03:33:33Z"
    }
}
```

点击发送请求
![](https://static.efur.top/img/2026/05/3ea938c89d58ef624c558ab1ad1d0ad9.png)

如果运行正常，下方的返回应该会有`secretText`\
`secretText`就是我们需要的密钥
:::caution
获取`secretText`之后尽快记下，若不记下 之后再也看不见了\
还得重新跑一遍流程
:::
![](https://static.efur.top/img/2026/05/116d2f09df0161016d79ef127301a98d.png)
此时再去 Microsoft Entra 管理中心刷新一下 应当就会看见这个新的密钥
![](https://static.efur.top/img/2026/05/9051c0420a52001f22f0f13b91b9ab7b.png)

## 4. 授权OpenList
之后就按照正常授权OpenList进行授权就好了\
打开以下URL进行授权\
租户ID和客户端ID Microsoft Entra 管理中心可以看见
```
https://login.microsoftonline.com/{租户ID或者common}/adminConsent?client_id={客户端ID}&redirect_uri=https://entra.microsoft.com/TokenAuthorize
```

此时你在授权你自己创建的应用程序，允许即可
![](https://static.efur.top/img/2026/05/e8baa77ca28792e8b9e2ca44c589ea49.png)

按照[文档](https://doc.oplist.org/guide/drivers/onedrive_app)，授权之后变为一片白屏，是正常的
![](https://static.efur.top/img/2026/05/0d6e8498d1ebe04126f8b0ffb5f6b8d6.png)

之后把你获取的数据填入到OpenList 添加存储中
![](https://static.efur.top/img/2026/05/5d4bd495ceca37c1a021de9d4cf8672c.png)
没有报错，大成功！
![](https://static.efur.top/img/2026/05/7f654f1050e1b762dddf86e2b36b7a3e.png)