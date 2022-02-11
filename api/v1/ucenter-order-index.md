 # 订单列表
 
 ****
     
**简要描述：** 

根据订单状态获取当前用户相应订单列表,请求参数请见参数

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/order/list `
  
**请求方式：**
- GET 

**参数：**

- 模糊查询

本查询主要是模糊查询 订单名称，商品名称，商品编号

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|status |是  |string |1 待付款,2 待发货,3 待收货 ,4 待评价 （status 不传则为全部订单）  |
|page |否  |string | 页码    |
|limit |否  |string | 每页多少条数据，不传默认为15条，如果要获取所有订单，请设置为足够大的值    |
|criteria |否  |string |  订单名称，商品名称，商品编号值，会模糊查询这三个字段值返回结果   |

 **返回示例**

``` 
{
    "status": true,
    "data": [
        {
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
            "submit_time": "2018-08-22 22:03:06",
            "type": 0,
            "channel": "ec",
            "channel_id": 0,
            "created_at": "2018-08-22 17:50:32",
            "updated_at": "2018-08-22 22:03:06",
            "from": "官网商城",
            "type_text": "普通订单",
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
                    "deleted_at": null,
                    "product": {
                        "id": 959,
                        "goods_id": 100,
                        "store_nums": 4,
                        "sku": "18172100373-1",
                        "sell_price": "49.00",
                        "market_price": "75.00",
                        "weight": null,
                        "is_show": 1,
                        "spec_ids": [
                            "15",
                            "40"
                        ],
                        "created_at": "2018-05-25 14:35:24",
                        "updated_at": "2018-08-22 22:03:06",
                        "deleted_at": null,
                        "goods": {
                            "id": 100,
                            "name": "本比小熊夏季宝宝背心2018新款休闲百搭夏装潮衣",
                            "goods_no": "18172100373",
                            "brand_id": 10,
                            "model_id": 3,
                            "min_price": "49.00",
                            "max_price": "49.00",
                            "sell_price": "49.00",
                            "market_price": "75.00",
                            "min_market_price": "75.00",
                            "weight": null,
                            "store_nums": 50,
                            "img": "https://cdn.viperky.com/storage/images/20180525/fBOKr15rw6.png",
                            "content": "<p><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071753374.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071491575.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071127561.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071824219.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072775994.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072304864.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072522432.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072842042.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073939546.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073467122.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073881449.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073516859.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073910114.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074255636.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074464478.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074314989.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074443772.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074233151.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/></p>",
                            "contentpc": null,
                            "sync": 0,
                            "comment_count": 0,
                            "visit_count": 0,
                            "favorite_count": 0,
                            "sale_count": 11,
                            "grade": 0,
                            "tags": "",
                            "keywords": "",
                            "description": "",
                            "is_del": 0,
                            "is_largess": 0,
                            "is_commend": 0,
                            "is_new": 0,
                            "collocation": null,
                            "extra": "{\"video\":{\"status\":\"0\",\"url\":\"\"}}",
                            "created_at": "2018-05-25 14:35:24",
                            "updated_at": "2018-05-28 15:10:23",
                            "deleted_at": null
                        }
                    }
                }
            ],
            "shippings": [],
            "adjustments": [],
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
    ],
    "meta": {
        "pagination": {
            "total": 1,
            "count": 1,
            "per_page": 10,
            "current_page": 1,
            "total_pages": 1,
            "links": []
        }
    }
}
```

