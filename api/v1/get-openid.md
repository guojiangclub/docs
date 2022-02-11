 # 获取openid
 
 ****
     
**简要描述：** 

小程序中进行以下操作需要 openid，所以需要小程序端需要调用此接口来获取 openid
1. 获取微信头像和昵称
2. 获取微信手机号
3. 微信支付

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/oauth/miniprogram/openid`
  
**请求方式：**

- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|code |是  |string | wechat code   |


 **返回示例**

``` 
  {
    "status": true,
    "data": {
      "openid":"xxxxx"
    }
  }
```

