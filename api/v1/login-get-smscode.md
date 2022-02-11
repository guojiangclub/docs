# 获取验证短信

****   
   
**简要描述：** 

- 发送短信验证码，在开发模式下，不会验证验证码的真实有效性，所以在手机验证码登陆时，开发模式下，可以任意输入验证么。

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/sms/verify-code`
  
**请求方式：**

- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|mobile |是  |string |手机号   |


 **返回示例**

``` 
 {
  "success": true,
  "type": "sms_sent_success",
  "message": "短信验证码发送成功，请注意查收"
}
```

**失败示例**

``` 
{
  "success": false,
  "message": '每60秒发送一次'
}
```



