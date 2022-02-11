 # 提交
 
 ****
     
**简要描述：** 

正式提交提单请求，进入待付款状态，如果是礼品无需支付金额，则直接进入待发货状态。

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/shopping/order/confirm `
  
**请求方式：**

- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|order_no |是  |string |订单编号，对订单的操作都以订单编号进行    |
|discount_id |否  |int | 促销ID    |
|coupon_id |否  |int | 优惠券ID    |
|address_id |是  |int | 用户地址ID    |
|note |否  |string | 用户留言字段    |


 **返回示例**

**说明**： 订单提交后，需要进入支付台页面，返回的Order数据未必使用

- 请求成功示例
```
{
    "status": true,
    "code": true,
    "data": {
        "order": {
            "id": 5,
            "user_id": 1,
            "order_no": "O2018082260691780535",
            "status": 1,
            "pay_status": 0,
            "distribution_status": 0,
            "count": 1,
            "items_total": 4900,
            "adjustments_total": 0,
            "payable_freight": 0,
            "real_freight": 0,
            "total": 4900,
            "accept_name": null,
            "mobile": null,
            "address": null,
            "address_name": null,
            "submit_time": {
                "date": "2018-08-22 22:03:06.403169",
                "timezone_type": 3,
                "timezone": "Asia/Shanghai"
            },
            "pay_time": null,
            "send_time": null,
            "completion_time": null,
            "accept_time": null,
            "message": null,
            "type": 0,
            "channel": "ec",
            "channel_id": 0,
            "cancel_reason": null,
            "note": null,
            "created_at": "2018-08-22 17:50:32",
            "updated_at": "2018-08-22 22:03:06",
            "deleted_at": null,
            "items": [
                {
                    "id": 5,
                    "order_id": 5,
                    "item_id": 959,
                    "item_name": "本比小熊夏季宝宝背心2018新款休闲百搭夏装潮衣",
                    "type": "iBrand\\Component\\Product\\Models\\Product",
                    "item_meta": {
                        "image": null,
                        "detail_id": 100,
                        "specs_text": "灰蓝 90"
                    },
                    "quantity": 1,
                    "unit_price": 4900,
                    "units_total": 4900,
                    "adjustments_total": 0,
                    "total": 4900,
                    "created_at": "2018-08-22 17:50:32",
                    "updated_at": "2018-08-22 17:50:32",
                    "deleted_at": null
                }
            ],
            "shippings": [],
            "adjustments": [],
            "comments": []
        }
    }
}
```

 **返回参数说明** 

- order 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|user_id |int   |订单所属用户  |
|status |int   |肯定为0，表示为一个临时的订单对象，新系统不会存入数据库  |
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

- discounts 该订单用户可选的促销优惠列表（需进一步完善现实格式）

- coupons 该订单用户可选优惠券列表（需进一步完善现实格式）



