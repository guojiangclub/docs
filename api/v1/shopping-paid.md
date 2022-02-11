# 验证支付
   
**简要描述：** 

- 用户完成支付操作后，跳转到成功页面，需要调用此接口验证支付状态
- 在 PAY_DEBUG 模式下，小程序可以直接传递 支付金额，来完成模拟支付

**请求URL：** 
- ` https://demo-open-admin.ibrand.cc/api/shopping/order/paid `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|order_no |是  |string | 订单编号   |
|amount |否  |int | 支付金额    |

 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "order": {
            "id": 6,
            "user_id": 1,
            "order_no": "O2018091242612364247",
            "status": 2,
            "pay_status": 1,
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
            "submit_time": "2018-09-12 09:08:55",
            "pay_time": {
                "date": "2018-09-12 09:28:35.824945",
                "timezone_type": 3,
                "timezone": "UTC"
            },
            "send_time": null,
            "completion_time": null,
            "accept_time": null,
            "message": null,
            "type": 0,
            "channel": "ec",
            "channel_id": 0,
            "cancel_reason": null,
            "note": null,
            "created_at": "2018-09-12 09:08:35",
            "updated_at": "2018-09-12 09:28:35",
            "deleted_at": null,
            "items": [
                {
                    "id": 6,
                    "order_id": 6,
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
                    "created_at": "2018-09-12 09:08:35",
                    "updated_at": "2018-09-12 09:08:35",
                    "deleted_at": null
                }
            ],
            "shippings": [],
            "adjustments": [],
            "comments": [],
            "payments": [
                {
                    "id": 1,
                    "order_id": 6,
                    "channel": "测试",
                    "channel_no": "",
                    "amount": 4900,
                    "status": "completed",
                    "details": "",
                    "paid_at": "2018-09-12 09:28:35",
                    "created_at": "2018-09-12 09:28:35",
                    "updated_at": "2018-09-12 09:28:35",
                    "deleted_at": null,
                    "channel_text": "",
                    "amount_yuan": "49.00"
                }
            ]
        },
        "payment": {
            "id": 1,
            "order_id": 6,
            "channel": "测试",
            "channel_no": "",
            "amount": 4900,
            "status": "completed",
            "details": "",
            "paid_at": "2018-09-12 09:28:35",
            "created_at": "2018-09-12 09:28:35",
            "updated_at": "2018-09-12 09:28:35",
            "deleted_at": null,
            "channel_text": "",
            "amount_yuan": "49.00"
        }
    }
}
```

