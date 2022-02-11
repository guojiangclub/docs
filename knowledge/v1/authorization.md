# 用户认证(Policy)编写规范

Laravel 官方文档： [用户授权系统](https://laravel-china.org/docs/laravel/5.5/authorization/1310)

## 注册 Policy

公司内部是使用模块化开发，因此 注册Policy（策略）建议在自身的模块中，无需在 `app/Providers/AuthServiceProvider` 中实现。

在自身模块包中注册Policy 的ServiceProvider 代码示例如下：

```php
    protected $policies = [
        Order::class => OrderPolicy::class,
    ];
    
    public function boot(GateContract $gate)
    {
        foreach ($this->policies as $key => $value) {
            $gate->policy($key, $value);
        }
    }
```

注意点： $policies 数组变量中类名称，请使用PHP7后的建议写法，而不是使用字符串的方式
```
'iBrand\Coterie\Core\Models\Coterie'=>'iBrand\Coterie\Core\Policies\CoteriePolicy',
```
好处就是后续方便寻找代码引用，而且重构时容易处理。

## 使用授权动作

在 Laravel 官方文档中提供了四种使用方式

1. 通过用户模型
2. 通过中间件
3. 通过控制器辅助函数
4. 通过 Blade 模板

目前在电商项目中，更多的使用方式是 1（通过用户模型） 和  3（通过控制器辅助函数）。

### 用户模型授权

电商中的代码示例，使用这种的方式的好处是，在授权失败后，可以进行更进一步的逻辑处理，并且返回指定的错误消息。
```php
if ($user->cant('submit', $order)) {
            return $this->faild('订单提交失败，订单内含有销售价低于商家价格保护设定的商品，请替换商品或联系商家');
        }
```

### 通过控制器辅助函数

代码示例：

```php
    public function update(Request $request, Post $post)
    {
        $this->authorize('update', $post);

        // 当前用户可以更新博客...
    }
```

这种方式的好处是 Laravel 自身为你处理了无论时的后续操作，如果动作不被授权，authorize 方法会抛出 Illuminate\Auth\Access\AuthorizationException 异常，然后被 Laravel 默认的异常处理器转化为带有 403 状态码的 HTTP 响应。

这个时候需要前端配合去处理，比如在请求 API 后，遇到403 的这种错误，统一提示无权操作。

好处就是简化了 后端 代码量，但是需要前端统一封装好处理这类问题。

### 总结

具体使用哪种方式，可以根据项目来决定，目前公司的内部项目中，前端并未统一处理AuthorizationException 403 异常，因此个人建议使用 **用户模型授权** 的方式来处理。
