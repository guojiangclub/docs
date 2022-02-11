 # 购物车添加商品
 
 **** 
     
**简要描述：** 

- 向购物车中添加商品。用户登录后才可使用该接口，未登录前需要前端本地存储。

- 支持批量添加商品

**请求URL：** 

- `https://demo-open-admin.ibrand.cc/api/shopping/cart `
  
**请求方式：**

- POST 

- 登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")


**参数：** 

重要说明：

- 购物车的商品可能是单品（SPU），也可能是多品（SKU）

- 因此ID值，SPU时值为SPU ID。 SKU时值为SKU ID值。

- 同时如果为SKU值时，请传递 attributes 字段，把SKU 相关规格数据传递进来。

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|index[id] |是  |int | 商品ID 或者SKU ID   |
|index[name] |是  |string | 商品名称    |
|index[qty]     |是  |int | 商品数量    |
|index[price]     |是  |int or float | 商品价格    |
|index[attributes]     |是  |数组 | 如：1[attributes][color]=红色  1[attributes][size]=M  1[attributes][sku]=xxxxx

 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "45dca4cd4c127ad499b153ec106b7672": {
            "__raw_id": "45dca4cd4c127ad499b153ec106b7672",
            "id": 959,
            "name": "支付测试商品",
            "qty": 1,
            "price": "49.00",
            "total": "49.00",
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
|status |string   |online 有效销售中，offline 已删除或下架，onhand 存库不够   |




