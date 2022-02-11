# prettus/l5-repository

> https://github.com/andersao/l5-repository

目前底层数据库查询依赖的 Repository 包

## 缓存

该包自带了查询缓存，降低性能，开启方式

### Cache Config

`config/repository.php` 配置文件中开启缓存模式，或者通过  `.env` 中设置  `REPOSITORY_CACHE_ENABLED` 

### Cache Usage

Implements the interface CacheableInterface and use CacheableRepository Trait.

```
use Prettus\Repository\Eloquent\BaseRepository;
use Prettus\Repository\Contracts\CacheableInterface;
use Prettus\Repository\Traits\CacheableRepository;

class PostRepository extends BaseRepository implements CacheableInterface {

    use CacheableRepository;

    ...
}
```

### 机制说明

1. 开启缓存后，只有使用 Repository 的 `all,paginate,find,findByField,findWhere,getByCriteria,` 内置方法查询时才会缓存
2. 开启缓存后，只有使用 Repository 的  `create,update,updateOrCreate,delete,deleteWhere` 等内置方法时才会刷新缓存。

### 代码解读

####  缓存查询结果

以下是对查询结果进行缓存，以 `find` 方法进行举例

```
    public function find($id, $columns = ['*'])
    {
        if (!$this->allowedCache('find') || $this->isSkippedCache()) {
            return parent::find($id, $columns);
        }

        $key = $this->getCacheKey('find', func_get_args());
        $minutes = $this->getCacheMinutes();
        $value = $this->getCacheRepository()->remember($key, $minutes, function () use ($id, $columns) {
            return parent::find($id, $columns);
        });

        $this->resetModel();
        $this->resetScope();
        return $value;
    }
```
1. 首选判断方法是不是可以缓存，同时判断是否请求的 url 中带了跳转缓存的参数，默认 `skipCache`,如 `&skipCache=true`
2. $this->getCacheKey 获取缓存 key，该方法首先会把 find() 方法所有的参数序列化，同时会序列化 Criteria 参数，最后 `$key = sprintf('%s@%s-%s', get_called_class(), $method, md5($args . $criteria . $request->fullUrl()));` 来组成一个唯一性的key，key三部分组成： Repository 类名名称，方法名称，参数+Criteria+请求完整的url 进行 md5 加密后的key。
3. 获取缓存的时间。
4. 缓存住结果。
5. 序列化成 model 对象返回。

问题：
1. key 是通过 CacheKeys 类进行文件缓存，缓存在  `framework/cache/` 目录下，这个类里变量是静态数组，所以后续上 swoole 是否会导致内存溢出，需要注意。

#### 更新缓存

调用 BaseRepository 方法中的 `create,update,updateOrCreate,delete,deleteWhere` 时会刷新缓存。

核心代码：`event(new RepositoryEntityUpdated($this, $model));` 触发这类事件，去清除缓存。

> 所有如果使用了缓存查询，在新增数据的必须使用 Repository 的以上方法，去触发缓存更新，不可直接使用 Molde::create 方式。



