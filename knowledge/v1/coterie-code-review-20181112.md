#  圈子 Code Review 20181112

### 1. getRecommend() 

1. 业务逻辑更改下，不需要分页了。默认把所有推荐的圈子拿出来，然后使用 Laravel Collection 的方法随机取5条，返回给前端。 $limit 参数可以接收，就是随机几条。
2. 如果没有推荐圈子，也不用去再随机取5条了，就留空。降低复杂度。
3. getRecommendCoterie（） 的逻辑代码改成 whereNotNull('recommend_at') 即可。


### 2. Repository 中多余的 query 嵌套
```php
        return $this->with('user')->scopeQuery(function ($query)  use($name){
            $query = $query->Where(function ($query) use($name) {
                $query = $query->where('name','like','%'.$name.'%');
            });
            return $query->orderBy('recommend_at','desc')->orderBy('created_at', 'desc');

        })->paginate($limit);
```
可以改成：
```php
return $this->with('user')->scopeQuery(function ($query)  use($name){
            return $query->where('name','like','%'.$name.'%');
        })->orderBy('recommend_at','desc')->orderBy('created_at', 'desc')->paginate($limit);
```
Repository 中有许多类似多余嵌套 query 的写法，请自行检查移除多余代码。

### 3. CoterieRepositoryEloquent::getCoterieByUserID 

这个是返回用户已加入的圈子，返回圈子的基础信息和圈主信息即可。

- 圈主信息已经通过 `with('user')` 获取

所以下面的代码并不需要 `with('member')` , 使用 WhereHas 即可。

```php
            $query = $query->with(['member' => function ($query) use ($user_id) {

                return $query->where('user_id', $user_id);

            }]);
```

### 4. 新增根据url获取链接的标题，图片，描述等

$router->get('content/query/link', 'ContentController@queryLink');

返回数组：link,title,descritption,img 。

- description 是 html  header 中的 description meta.

业务逻辑：用户输入url后，前端会发起请求，后端返回以上数据给前端，前端展示。前端作为content内容直接传递过来。

### 5. ContentController::storeDefault()

改进的点：
1. 直接使用 store 即可，和 Laravel Resource 的方法命名保持一致。而且其他 Controller 也是这样命名的。 
2. img_list，tags_list，audio_list 等参数，前端应该使用数组传过来而不是逗号分隔的字符串，这样的优势就是可以在 Model 中直接设置 Attribute 可以实现自动 JsonEncode；
3. CoterieService::updateTypeCountByID 请使用 Laravel increment 来实现。

备注：
问题2，使用该控制器中的 update 方法。

### 6. 事务代码在异常中没有执行 rollBack() 回滚

请在所有调用了 beginTransaction 启用事务的地方，在 catch Exception 中调用 rollBack 回滚事务函数。

请自行查找这类地方，比如 `ContentService::created()`

### 7. 热门标签，内容关联标签模块待讨论最佳实践。

### 8. ContentController::setContentRecommendedAt()

一个控制器里操作设置推荐和取消推荐，需要和前端确认那种模式更合适，是区分成两个请求还是单个请求。

### 9. ContentService::setContentRecommendedAt()

设置内容为推荐内容这里太复杂了，逻辑没太明白。

```php
if(empty($content->recommended_at) AND $type==0){
    return null;
 }
if($content->recommended_at AND $type==1){
    return null;
}
```

### 10. CommentRepositoryEloquent::getCommentsByContentID()

Repository 中多余的 query 嵌套，发现一处，其他自行查找

### 11. MemberController::index

这里应该是显示圈子的所有成员，有三个部分组成：圈主，嘉宾，和普通成员。

目前实现逻辑时，在所有数据里面去切片，太过于复杂。

建议按如下处理：

把圈主，嘉宾和普通成员通过三个字段返回给前端即可，普通成员部分使用分页获取即可。

### 12. MemberController::store()

业务逻辑：

如果用户没有被踢出过，任何人都是可以加入圈子的。所以第一步应该是判断用户是否被踢出过该圈子。

目前是通过 `CoterieRepositoryEloquent::getCoterieMemberByUserID()` 方法，这里过于复杂，绕弯了。

应该直接使用 `MemeberRepositoryEloquent` 去判断用户在该圈子是不是被删除过，如果没有被删除过，则是可以加入圈子的，这样一个简单的 where 即可。















