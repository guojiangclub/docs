# Swoole 集成注意事项


## Dingo Api导致跨域HTTP中间件不能使用

https://github.com/hhxsv5/laravel-s/issues/28

目前针对H5，小程序等接口会存在跨域的问题，目前使用第三方包来解决跨域的问题。

### 解决办法

#### 1. 使用 nginx cors

可以使用 nginx cors 来实现跨域，不使用第三方功能包。

```
location / {
    add_header Access-Control-Allow-Origin *;
    add_header Access-Control-Allow-Methods 'GET, POST, OPTIONS';
    add_header Access-Control-Allow-Headers 'DNT,X-Mx-ReqToken,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Authorization';

    if ($request_method = 'OPTIONS') {
        return 204;
    }
}
```

#### 2.  在 laravels.php 中重置 ServiceProvier

```
'register_providers' => [
        /* middleware service providers */
        Dingo\Api\Provider\DingoServiceProvider::class,
        Dingo\Api\Provider\HttpServiceProvider::class,
        /* auth service providers */
        Illuminate\Auth\AuthServiceProvider::class,
        App\Providers\AuthServiceProvider::class,
        Tymon\JWTAuth\Providers\LaravelServiceProvider::class,
],
```

## Controller 中不能初始化变量，导致常驻内存不会改变值

https://github.com/hhxsv5/laravel-s/issues/112


### 解决办法： 

1. 在所有的 Controller 中不进行变量初始化操作
2. 使用中间件重置 Controller 对象。

```    
    public function handle($request, Closure $next)
    {
        if (PHP_SAPI === 'cli') {
            unset(Route::current()->controller);
        }
        return $next($request);
    }

```

