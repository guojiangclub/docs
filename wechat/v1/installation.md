
# 体验&部署

****

## 体验

//TODO: 

## 部署


### 下载源码

```
git clone https://github.com/ibrandcc/laravel-wechat-platform.git
```

### Laravel 常规安装

以下步骤基本是 Laravel 项目安装需要执行的必须步骤

#### 安装依赖包

我们为了方便大家使用，在项目的 `composer.json` 中已经默认使用了国内的 `composer` 镜像源，感谢 [laravel-china](https://laravel-china.org)

下载好源码后，直接执行

```
composer install -vvv
```

#### 设置 .env

.env 文件中的数据库部分设置成自己开发的数据库配置

```
cp .env.example .env
```

####  应用密钥

通过以下命令来生成应用密钥，密钥值在 `.env` 文件 `APP_KEY`
```
php artisan key:generate
```

#### 发布相关资源

执行 `publish` 命令发布所有相关的资源，包含配置项，静态资源等。

```
php artisan vendor:publish --all
```

#### 设定公共磁盘软连接

Laravel 中上传文件通常是存储在 `storage/app/public` 目录下，该目录下的文件可以通过 `php artisan storage:link` 命令软连接到 `public` 目录下，以供外部访问。

更多细节请见：[文件系统](https://laravel-china.org/docs/laravel/5.5/filesystem/1319)

#### 安装 Passport

基于 Laravel Passport 实现，所以需要执行 `php artisan passport:install` 安装 Passport

#### 生成数据库

```
php artisan migrate
```

### 配置

#### 生成管理菜单

```
php artisan ibrand:backend-install
php artisan ibrand-wechat-platform:install
```


#### 配置微信第三方平台账号

请在 .env 文件中配置微信第三方平台账号信息

```
WECHAT_OPEN_PLATFORM_APPID=             //微信开放平台AppID
WECHAT_OPEN_PLATFORM_SECRET=	        //微信开放平台AppSecret
WECHAT_OPEN_PLATFORM_TOKEN=             //消息校验Token
WECHAT_OPEN_PLATFORM_AES_KEY=           //消息加解密Key
```

### 登陆后台

域名/admin 

用户名: admin 密码: admin




