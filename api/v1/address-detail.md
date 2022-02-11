 # 收货地址详情
 
 ****
     
**简要描述：** 

获取收货地址详细信息 


**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/address/{id} `
  
**请求方式：**
- GET 

- 登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")

 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "id": 3,
        "user_id": 1,
        "accept_name": "测试修改收货地址",
        "mobile": "18899997777",
        "province": 430000,
        "city": 430100,
        "area": 430103,
        "address_name": "湖南省 长沙市 天心区",
        "address": "详细街道地址",
        "is_default": 1,
        "created_at": "2018-08-23 19:53:12",
        "updated_at": "2018-08-23 20:02:51",
        "deleted_at": null
    }
}
```


