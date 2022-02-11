 # 购物车修改商品
 
 **** 
     
**简要描述：** 

修改购物车的商品数据属性

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/shopping/cart/{id}`

说明： id 参数为必传参数，为购物车商品的 `__raw_id`

**请求方式：**

- PUT 

**参数：** 

说明：通常都是更改购物车中某个商品的数量

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|attributes[qty]     |是  |数组 | 必须传入修改购物车商品的数量，一般购物车中也是修改某个商品的数量 |
|attributes     |否  |数组 | 数组形式的额外信息，举例：attributes[size]=L |

 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "__raw_id": "45dca4cd4c127ad499b153ec106b7672",
        "id": 959,
        "name": "支付测试商品",
        "qty": "3",
        "price": "49.00",
        "total": 147,
        "__model": "iBrand\\Component\\Product\\Models\\Product",
        "type": "sku",
        "status": "online",
        "sku": "18172100373-1",
        "size": "90",
        "color": "孔雀蓝",
        "market_price": "75.00",
        "channel": "normal"
    }
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|__raw_id |string   |购物车ID  |
|id |int   |商品ID  |
|name |string   |商品名称  |
|qty |int   |商品数量  |
|price |string   |商品价格  |
|total |int or float   |总价格  = qty* price|
|color |string   | 为attributes 中的属性名称  |
|size |string   |为attributes 中的属性名称   |
|sku |string   |为attributes 中的属性名称   |

