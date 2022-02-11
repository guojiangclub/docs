 # 订单详情
 
 ****
     
**简要描述：** 

根据订单编号(order_no)获取订单详情，该接口除返回订单自身信息外，还会返回如下关联信息：

1. items: 订单商品数组

2. shippings: 订单物流信息数组，一个订单可能包含多个物流信息。


**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/order/{orderno} `
  
**请求方式：**
- GET 


 **返回示例**

``` 
{
    "status": true,
    "data": {
        "id": 1,
        "user_id": 1,
        "order_no": "O2018083126717726534",
        "status": 1,
        "pay_status": 0,
        "distribution_status": 0,
        "count": 1,
        "items_total": 4900,
        "adjustments_total": 0,
        "payable_freight": 0,
        "real_freight": 0,
        "total": 4900,
        "submit_time": "2018-08-31 09:49:07",
        "type": 0,
        "channel": "ec",
        "channel_id": 0,
        "created_at": "2018-08-31 09:48:56",
        "updated_at": "2018-08-31 09:49:07",
        "from": "官网商城",
        "type_text": "普通订单",
        "items": [
            {
                "id": 1,
                "order_id": 1,
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
                "created_at": "2018-08-31 09:48:56",
                "updated_at": "2018-08-31 09:48:56",
                "deleted_at": null
            }
        ],
        "shippings": [],
        "accept_name": "",
        "mobile": "",
        "address": "",
        "address_name": "",
        "pay_time": "",
        "send_time": "",
        "completion_time": "",
        "accept_time": "",
        "message": "",
        "cancel_reason": "",
        "note": "",
        "deleted_at": ""
    }
}
```

**返回参数说明** 

-  **订单基础信息**

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|order_no |string   | 订单编号 |
|count |int | 整个订单商品数量 |
|status |int |订单状态。 |
|produce_status |string |生产状态|
|pay_type |string |暂未使用，历史遗留 | 
|pay_status |string |暂未使用，历史遗留 |
|items_total |int |所有商品的销售总价 |
|adjustments_total |int |所有商品的优惠总价 |
|total |int | 整个订单应付金额 |
|accept_name |string |收货人姓名 |
|from |string |订单来源 |
|type_text |string |订单类型 |
|payment_text |string |支付方式 |
|adjustment_point |int |该订单使用了多少积分 |
|group_item_count |int |如果值为1，表示只有一条发货信息；否则为多条物流信息，订单item根据group_order_item来显示 |
|can_refund|bool|能否进行售后：true  false|



-  **items （订单商品）信息**

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|order_id |int   | 订单ID |
|item_id |int | 商品ID，根据 type 字段来确定是 SPU ID 还是 SKU ID |
|type |string | 目前会返回一个包含命名空间类字符串，如：ElementVip\\Component\\Product\\Models\\Product ，表示一个SKU 商品类型。 |
|item_name |string |商品名称 |
|item_meta |json |存储商品的额外信息，以 json 字符串形式存储。目前常用的有： image: 商品图片的url， specs_text：用户选择的规则数据  detail_id: 商品详情需要的ID（goods_id） |
|quantity |int |该商品的数量 |
|unit_price |int |该商品的销售单价 |
|units_total |int | units_total = quantity* unit_price |
|adjustments_total |int |优惠金额，通常为负数 |
|total |int | total =  units_total + adjustments_total|
|refund_btn|array|售后按钮信息|
|is_refunded|bool|true 不显示新的申请售后按钮；false 并且order.can_refund=true,显示申请售后按钮|

-  **shippings 订单物流信息**

|参数名|类型|说明|
|:-----  |:-----|----- |
|order_id |int   | 订单ID |
|tracking |string | 物流单号 |
|delivery_time |string | 发货时间|
|name |string |物流公司名称，如：圆通快递 |


