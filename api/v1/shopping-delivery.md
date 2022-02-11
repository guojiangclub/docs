 # 发货
 
 ****
    
**简要描述：** 

发货接口，通过传输订单号实现模拟发货

> 该接口是为了方便调试提供的，正式环境中不需要该接口

**请求URL：** 

- `https://demo-open-admin.ibrand.cc/api/shopping/order/delivery `
  
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
    "data": null
}
```

