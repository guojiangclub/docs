# 商品海报
    
**简要描述：** 

- 商品详情页的海报分享

> 该功能是使用 [laravel-miniprogram-poster](https://github.com/ibrandcc/laravel-miniprogram-poster) 实现，觉得好用欢迎 star ！ : )

**请求URL：** 

- `https://demo-open-admin.ibrand.cc/api/store/detail/{id}/share/img `
  
**请求方式：**

- GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| page| 是  | string | 从小程序获取 pages   |

 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "url": "http://open-api.dev/storage/share/20180925/share_goods_7b2a490e1660c404960bca45d677ff4c.png",
        "path": "20180925/share_goods_7b2a490e1660c404960bca45d677ff4c.png"
    }
}
```



