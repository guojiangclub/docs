# 结算

** 简要描述：** 

在购物车中选中商品后进行结算操作，结算会做以下几件事情：
1. 检查结算商品状态和库存
2. 创建 Order 对象并存入数据库
3. 返回当前用户默认地址
4. 返回该订单可用的促销活动数据
5. 返回该订单可用的优惠券数据

> 暂未支持商品详情页直接下单

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/shopping/order/checkout `
  
**请求方式：**
- POST 

**认证参数：**

登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")

**参数：** 

- 购物车结算

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|cart_ids |否  |array |  购物车选中商品的 raw_id  |

用于传递购物车中选中的商品，如未传该参数，默认获取到购物车中所有的商品

 **返回示例**

- 请求成功示例

1. items 里的第一个商品是一个动态SKU商品。

```
{
    "status": true,
    "code": 200,
    "data": {
        "order": {
            "user_id": 9,
            "status": 0,
            "order_no": "O2018100518505451648",
            "items_total": 4900,
            "total": 4900,
            "count": 1,
            "updated_at": "2018-10-05 14:52:44",
            "created_at": "2018-10-05 14:52:44",
            "id": 23,
            "payable_freight": 0,
            "items": [
                {
                    "quantity": 1,
                    "unit_price": 4900,
                    "units_total": 4900,
                    "total": 4900,
                    "item_id": 959,
                    "type": "iBrand\\Component\\Product\\Models\\Product",
                    "item_name": "本比小熊夏季宝宝背心2018新款休闲百搭夏装潮衣",
                    "item_meta": {
                        "image": null,
                        "detail_id": 100,
                        "specs_text": "灰蓝 90"
                    },
                    "order_id": 23,
                    "updated_at": "2018-10-05 14:52:44",
                    "created_at": "2018-10-05 14:52:44",
                    "id": 24,
                    "order": null
                }
            ],
            "adjustments": [],
            "comments": []
        },
        "discounts": false,
        "coupons": [],
        "address": null,
        "best_discount_id": 0,
        "best_coupon_id": 0,
        "best_coupon_adjustment_total": 0,
        "best_discount_adjustment_total": 0
    }
}
```

 **返回参数说明** 

- order 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|user_id |int   |订单所属用户  |
|status |int    |肯定为0，表示为一个临时的订单对象  |
|order_no |string   |订单编号  |
|items_total |int  |订单中商品的销售总价，单位为分  |
|total |int  |订单总价=items_total + adjusment_total ，单位为分 |
|count |int  |商品总数量  |


- items 订单记录中的商品列表

|参数名|类型|说明|
|:-----  |:-----|-----  |
|quantity |int   |该商品的数量  |
|unit_price |int   |商品的销售价格  |
|units_total |int   |商品的销售总价 = unit_price * quantity  |
|total |int  |商品的最终价格 =  units_total + adjusment_total（优惠价格，为负数） |
|item_id |int  |关联的商品ID或者SKU id |
|type |string  |关联的模型名称  |
|item_name |string  |商品名称  |
|item_meta[detail_id] |string  |商品详情页的ID  |
|item_meta[image] |string  |商品的图片url  |
|item_meta[specs_text] |string  |规格文本描述  |


