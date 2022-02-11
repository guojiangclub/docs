 # 默认收货地址
 
 ****
     
**简要描述：** 

获取当前用户默认收货地址信息 ，会根据 token 自动获取

**请求URL：** 

- `https://demo-open-admin.ibrand.cc/api/address/default `
  
**请求方式：**
- GET 

- 登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")



 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "id": 2,
        "user_id": 1,
        "accept_name": "顾欢",
        "mobile": "18088888888",
        "province": 130000,
        "city": 130200,
        "area": 130207,
        "address_name": "河北省 唐山市 丰南区",
        "address": "长春永川区",
        "is_default": 0,
        "created_at": "2018-08-22 21:52:17",
        "updated_at": "2018-08-22 21:52:17",
        "deleted_at": null
    }
}
```

