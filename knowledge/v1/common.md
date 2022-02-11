# Common 包介绍

[ibrand/common](https://github.com/ibrandcc/common) 该包目前为 iBrand 核心基础包，主要包含一些常用方法。目前包含以下模块：

1. 基础的控制器，适配 Laravel API Resource，进行了适当封装。
2. WechatController： 目前只包含了返回 JSSDK 的封装，可以通过第三方平台，也可以直接通过 Easywechat 直连微信获取 jssdk 数据。
3. 封装了基础的 API Resource 包 
4. 封装了调用第三方平台接口。
5. 基于 Easywechat 继续完善封装了微信相关接口，不去使用 Laravel-easywechat ,因为无法适应后台数据库设置appid，appscret 以及 swoole。
6. 封装了常用 help 方法。
7. ibrand/app.php 的配置文件设定

## 基础控制器

源码：[Controller](https://github.com/ibrandcc/common/blob/master/src/Controllers/Controller.php)

后续所有的控制器都可以继承此控制器，封装了常见的方法，但是不适配 dingo/api，仅适用于 [API Resource](https://learnku.com/docs/laravel/5.8/eloquent-resources/3935)

已经处理好了所有常见的方法（和 dingo api 之前的几个方法一致）：

- success
- failed
- item
- collection
- paginator

## WechatController

因为获取 JSSDK 是微信中 H5 应用中都需要使用的，所以抽取到 Common 包中来。

可通过 `ibrand.platform.enabled_jssdk` 配置来决定是否启用微信第三方平台来获取 JSSDK 数据。

具体请参见源码 [WechatController](https://github.com/ibrandcc/common/blob/master/src/Controllers/WechatController.php)

> 使用微信第三方平台，H5 所在的域名必须在第三方平台的网页开发域名中
> [1、在申请第三方平台时填写的网页开发域名，将作为旗下授权公众号的JS SDK安全域名 ](https://open.weixin.qq.com/cgi-bin/showdocument?action=dir_list&t=resource/res_list&verify=1&id=open1421823488&token=&lang=)

## API Resource

已经对 Laravel 5.5 之后的 [API Resource](https://learnku.com/docs/laravel/5.8/eloquent-resources/3935) 进行了常用的应用封装

而且适配了 dingo/api 的格式，这样前端不需要做任何改动，就可以无缝切换。

## 微信第三方平台调用封装

目前 iBrand 产品体系下，所有的微信公众都需要客户授权我们的第三方平台，因为在调用第三方平台时有些常用的方法，在此进行了统一封装。

之前在各个项目的使用方法需要逐步废弃，替换改包里的方法。

### ibrand.platform config

可以通过 `ibrand.platform` 配置文件来配置 iBrand 第三方平台的 `url,client_id,client_secret`


### platform_application() 辅助函数

可以通过 `platform_application()` 帮助函数来快速获得 platform application 实例。

可以通过 `platform_application()->getJsConfig($url,$appid)` 等链式函数来直接调用。

> 已经解决了编辑器的函数提示功能，具体请参见 [Application](https://github.com/ibrandcc/common/blob/master/src/Platform/Application.php) 文件头

```php
/**
 * Class Application.
 * @method Client            getOauthUrl($redirectUri,$appid)
 * @method Client            getUser($appid,$openid)
 * @method Client            createMiniQrcode($appid, $page, $width, $scene, $type = 'share', $storage = 'public', $uuid)
 * @method Client            sendTemplateMessage($appid,$message)
 * @method Client            getJsConfig($url, $appid)
 */
class Application {

}
```

### client 类

如果需要添加新的调用函数方法，请添加到 [Client](https://github.com/ibrandcc/common/blob/master/src/Platform/Client.php) 类，具体使用请参加类中的其他方法。

## Easywechat

目前微信相关的开发调用都是基于 Easywechat，目前主要因为以下原因，我们最好不要直接使用 Laravel 版本的 Easywechat

1. Laravel 版 Easywechat 是在 config 中直接单例了对象，无法适用我们通过后台把公众号配置存储在数据库的问题。因为 在 ServiceProvider中的 Register 方法还无法拿到数据库数据。
2. 单例实例对后续集成 Swoole 不利，特别后续的 Saas 版本。

**该模块文件请参加 Wechat 目录，但是目前该模块还没有完整实现，可以使用如下方法：**

```
use iBrand\Common\Wechat\Factory

Factory::officialAccount('default');

$config=['app_id'=>'','app_secret'=>'']
Factory::miniProgram($config);
```

也可以通过配置 `ibrand.wechat` 配置文件来配置相关设置

## helpers.php

封装了如下常用方法：
- platform_application
- is_mobile
- is_mail
- is_username
- api_prefix
- get_wechat_config





