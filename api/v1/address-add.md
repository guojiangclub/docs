 # 收货地址新增
 
 ****
     
**简要描述：** 

新增用户收货地址 

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/address `
  
**请求方式：**
- POST 


- 登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")


**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|accept_name |是  |string |收件人   |
|mobile |是  |string | 手机号码    |
|province     |是  |int | 省份编码    |
|city     |是  |int | 城市编码    |
|area     |是  |int | 区域编码    |
|address_name     |是  |string | 省市区中文名    |
|address     |是  |string | 详细地址    |
|is_default     |是  |int | 是否默认地址 (0.非默认 1.默认)    |


 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "accept_name": "测试名称",
        "mobile": "18899997777",
        "province": "430000",
        "city": "430100",
        "area": "430103",
        "address_name": "湖南省 长沙市 天心区",
        "address": "详细街道地址",
        "is_default": "1",
        "user_id": 1,
        "updated_at": "2018-08-23 19:53:12",
        "created_at": "2018-08-23 19:53:12",
        "id": 3
    }
}
```



