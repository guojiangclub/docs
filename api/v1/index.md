# 使用说明

> 本文因为时间久远，需要直接体验的请见 [体验与部署](<https://www.ibrand.cc/docs/api/v1>)



本 API 文档主要是给小程序前端工程师对接接口使用，在 iBrand 团队也是如此。

通常后端项目组会先写好接口，并且通过 Postman 完成测试，并且提供此类文档给前端工程师，前端工程师根据此类文档完成和后端接口的对接开发。

### 源码

API源码： [ecommerce-open-api](https://github.com/ibrandcc/ecommerce-open-api)
小程序源码：[miniprogram-ecommerce-open-source](https://github.com/ibrandcc/miniprogram-ecommerce-open-source)

欢迎大家 star 支持！ ： ）

### 环境

> 建议使用 Vagrant 作为 Laravel 的开发环境

```
$ git clone git@github.com:ibrandcc/ecommerce-open-api.git
$ cd src
$ composer install
$ cp .env.example .env
$ php artisan key:generate
$ php artisan passport:keys
```
> 暂时不执行 `php artisan migrate` 命令，因为我们已经提供了数据库文件，同时不执行 `php artisan passport:install` 命令，因为 `client` 已经存在数据库中。

#### 其他注意点

- `.env.example` 已经默认包含了 `dingo/api` 的配置，无需更改.
- `.env.example` 已经默认设置了支付调试`PAY_DEBUG=true`
- `.env` 中的 `APP_URL` 请改成你本地的开发的url，比如：`http://open.dmp.com`


### 数据库文件

数据库源文件可通过本文末尾联系我们进入到QQ群中进行下载。

> 数据库特意留了一些坑，在后续我们通过文章分析陆续解决，请莫介意!  ： ）

### Postman

Postman 非常适合作为本地 API 调试与测试的工具，它能提供功能强大的 Web API 和 HTTP 请求。

可以通过 [官网下载][1] 或者百度网盘下载：https://pan.baidu.com/s/1bqVD5MJ 密码：4lku

> Postman 需要登录后才可使用，所以可以免费注册账号后登录，也可以直接使用 Google 账号登录。

为了方便大家测试我们已经把 Postman 文件导出来，可通过下述链接下载：

链接: https://pan.baidu.com/s/17EtkM1QCA9jVRzIQ6sdzGg  提取码: 9m54

![Postman API](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/postman/postman1.png)

### 扫码体验

![体验小店](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/miniprogramcode/1.jpg)

### 联系我们

![二维码](https://iyoyo.oss-cn-hangzhou.aliyuncs.com/post/%E4%BA%8C%E7%BB%B4%E7%A0%81.jpg)