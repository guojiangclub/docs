# Laravel Controller 编写原则

Laravel controller 用于处理 http 请求，执行响应逻辑后，返回相对数据给前端。所以最主要的职责是接收收据，处理业务和数据，返回数据。

个人总结的编码逻辑应该如下：
1. 权限校验：接收数据后，第一步应该是校验权限，比如查看用户是否又发表，修改等权限。
2. 数据校验： 验证完权限后，校验数据的完整性和正确性。
3. 处理业务逻辑：如果是非常简单，又不通用的业务逻辑，可以直接在控制器中完成，不需要新增 Service 层。
4. 返回数据。

下面以代码示例说明。

## 权限校验

有些操作用户是没有权限的，所以第一步就是权限校验，如果有权限才继续，没权限都不用继续下去。

在Laravel 中应该是用  [授权系统](https://laravel-china.org/docs/laravel/5.5/authorization/1310)  来完成。

举例：

比如只有圈主才能修改圈子的内容，在接收前端数据后，首先应该判断是否有权限修改

```php
    public function update()
    {
        $this->authorize('update', $coterie);

        // 当前用户可以更新圈子
    }
```
在 Laravel 文档中推荐 4中方式：
1. 通过用户模型
2. 通过中间件
3. 通过控制器辅助函数
4. 通过 Blade 模板

目前我们系统的架构中，推荐的方式应该是1和3。在电商中我采用更多的是方式1。

> 方式3 是控制器中的辅助函数，如果授权失败会自动抛出异常返回错误，不需要编写 if，然后再返回结果，具体可自行验证。

## 数据校验

完成权限验证后，是对请求中的数据进行验证，这里也推荐使用 Laravel 的  [表单验证](https://laravel-china.org/docs/laravel/5.5/validation/1302) 来完成。

拿数据圈 `CoterieController@store` 来示例说明：

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|name |是  |string | 圈子名称 |
|description |是  |string | 圈子描述 |
|avatar     |是  |string | 圈子头像 |
|duration_type     |是  |string | 到期类型  |
|notice     |否  |string | 入圈声明 |
|price     |是  |int | 价格，非必传参数，cost_type=free 时可不传入 |
|cost_type     |是  |string | 必传参数，因为只会是两种类型中的一种。 |

```php
    $this->validate($request, [
        'name' => 'required|unique:coterie|max:255',
        'description' => 'required',
        'avatar' => 'required',
        'duration_type' => 'required',
        'price' => 'required',
        'cost_type' => 'required',
    ]);
```

执行 Controller validate 方法，如果失败的话，Controller 会自动返回影响的错误结果提示。

## 处理业务逻辑

在创建数据库的业务中，完成所有数据校验后，就是创建 Coterie 数据，同时在 Member 表中新建一条 type = owner 的记录。

在没有其他重复业务逻辑的情况下，可以不把该逻辑抽象成 Service 层。

```php
$coterie = $this->coterie->create($input);
$this->member->create(['coterie_id'=>$coterie->id,$user_id=$user->id,'type'=>Member::OWNER_TYPE]);
```

## 返回数据结果

创建圈子，完成圈子后，直接返回数据即可。

```php
$this->success($coterie);
```






