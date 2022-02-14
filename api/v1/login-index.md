# 登陆流程

### 简介

目前在小程序中可以通过用户授权直接拿到头像昵称或手机号，几乎所有的小程序都是通过以上方式来创建用户体系，同时返回 `token` 给前端来达到登陆目的，而 iBrand 产品中也是类似的流程。

### 流程图

在 iBrand 产品用户体系中，我们是以手机号来作为用户的唯一识别，所以当需要用户进行登陆后才操作的动作时，我们会提醒用户进入登陆流程，流程如下：

![小程序登陆流程](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%99%BB%E9%99%86%E6%B5%81%E7%A8%8B.jpg)


### API 接口

1. [快捷登陆](https://guojiang.club/docs/api/v1/login-quick)：用户进入登陆流程时，小程序首先把 code 通过该接口传给后端，后端通过 code 去拿 openid，并且判断该 openid 是否存在用户，如果已经存在则直接返回 token，如果不存在则返回 openid 给前端。
2. [微信手机登陆](https://guojiang.club/docs/api/v1/login-mobile)：通过微信授权手机号直接登陆创建账号返回 token 给前端。
3. [短信登录](https://guojiang.club/docs/api/v1/login-sms)：如果用户不通过微信授权手机号登陆，用户可以继续通过[发送短信](https://guojiang.club/docs/api/v1/login-get-smscode)进行短信登陆。

### 扫码体验

![体验小店](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/miniprogramcode/1.jpg)


### UI 示例

![登陆UI1](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/login/0101.png)![登陆UI2](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/login/0102.png)![登陆UI3](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/login/0103.png)![登陆UI4](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/login/0104.png)![登陆UI5](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/login/0105.png)![登陆UI6](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/login/0106.png)


### 联系我们

![二维码](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/%E4%BA%8C%E7%BB%B4%E7%A0%81.jpg)