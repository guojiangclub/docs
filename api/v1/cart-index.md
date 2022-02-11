 # 购物车商品列表
 
 **** 
     
**简要描述：** 

获取购物车所有商品数据

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/shopping/cart `
  
**请求方式：**

- GET 

 **返回示例**

``` 
{
  "8a26bdc6d238ca3bb3bc771915b900e1": {
    "__raw_id": "8a26bdc6d238ca3bb3bc771915b900e1",
    "id": 38,
    "name": "Item name",
    "qty": 5,
    "price": 100,
    "total": 500,
    "__model": null,
    "color": "red",
    "size": "M",
	"channel": "normal"
  },
  "035b14fe1595dc2f7c17ccb303ea5832": {
    "__raw_id": "035b14fe1595dc2f7c17ccb303ea5832",
    "id": "1",
    "name": "我的背包商品",
    "qty": "10",
    "price": "100",
    "total": 1000,
    "__model": null,
    "color": "红色",
    "size": "L",
    "sku": "877257018061",
	"channel": "employee"
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
|channel |string   |商品类型：normal为默认值，employee为内购商品|


  