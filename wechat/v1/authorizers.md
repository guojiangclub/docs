  
# 获取已授权的公众号列表
****    
    
**简要描述：** 

- 获取已授权的公众号列表

**请求URL：** 
- `http://demo-wechat-platform.ibrand.cc/api/authorizers?client_id={client_id}`
  
**请求方式：**
- GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|client_id |是  |string | 客户凭证ID [生成客户凭证](/docs/{{type}}/{{version}}/client) |
|type |是  |int |  1微信公众号，2小程序|
|call_back_url |否  |string |  设置接收消息和事件回调地址|


 **返回示例**

``` 
[
    {
        "id": 8,
        "appid": "wx9134970bbbbfdsfdsfd",
        "service_type_info": 2,
        "verify_type_info": 0,
        "refresh_token": "refreshtoken@@@hbml89sdfdsfdsfds",
        "func_info": "dsfsfsdfsdfsdf",
        "client_id": 4,
        "nick_name": "ibrand",
        "head_img": "http://xxx.com",
        "user_name": "gh_e719eb784a9b",
        "principal_name": "ibrandcc",
        "qrcode_url": "http://xxx.com",
        "call_back_url": "http://call_back_url.com",
        "created_at": "2018-04-24 07:19:05",
        "updated_at": "2018-08-27 08:48:13",
        "type": 1,
        "mini_info": null
    }
]
```


 **说明** 

|参数名|类型|说明|
|:-----  |:-----|-----|
|service_type_info |string | 授权方公众号类型，0代表订阅号，1代表由历史老帐号升级后的订阅号，2代表服务号  |
|call_back_url|string| 公众号回调。
|verify_type_info|string| 授权方认证类型|
|type|string| 1公众号，2小程序|


 **注意** 
第三方只接收消息或事件，发送数据到回调地址。
- 默认事件回调地址：{call_back_url}/wechat_call_back/event
- 默认消息回调地址：{call_back_url}/wechat_call_back/message


  **** 




