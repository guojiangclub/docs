 # 取消订单
 
 ****
    
**简要描述：** 

用户提交订单后，未付款前可主动取消订单。

**请求URL：** 

- `https://demo-open-admin.ibrand.cc/api/shopping/order/cancel`
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|order_no |是  |string |订单编号   |


 **返回示例**

``` 
{
  "status": true,
  "code": 200,
  "message": "",
  "data": []
}
```


