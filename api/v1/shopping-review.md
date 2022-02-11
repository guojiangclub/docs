 # 评价
 
 ****
     
**简要描述：** 

- 只有用户确认收货后才允许用户评价订单，评价操作是针对订单中的每一项商品进行评价操作

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/shopping/order/review `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|index[order_no] |是  |string |订单编号   |
|index[order_item_id] |是  |int | 用户选择评价的订单item    |
|index[contents]     |否  |string | 评价内容，可以不传，默认为空    |
|index[point]     |否  |int | 评价几颗星，不传入默认数值为5    |
|index[images]     |否  |array | 评论图片，可以不传    |

 **返回示例**

``` 
{
  "status": true,
  "code": 200,
  "message": "订单评价成功",
  "data": []
}
```



  