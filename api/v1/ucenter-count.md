# 个人中心汇总数据   

**简要描述：** 

- 进入到个人中心的时候返回各种状态下的订单数量，优惠券数量等

**请求URL：** 
- ` https://demo-open-admin.ibrand.cc/api/users/ucenter `
  
**请求方式：**
- GET 

**参数：** 

无

 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "newCount": 1,
        "paidCount": 1,
        "deliveredCount": 0,
        "receiveCount": 0,
        "favCount": 1,
        "addressCount": 3,
        "couponCount": 0
    }
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|newCount |int   |待付款订单  |
|paidCount |int   |已付款待发货订单
|deliveredCount |int   |已发货待收货订单
|receiveCount |int   |已收货待评价订单
|favCount |int   |收藏数
|addressCount |int   |收货地址数
|couponCount |int   |优惠券数


