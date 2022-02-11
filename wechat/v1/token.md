  
# 获取token
 ****   
    
**简要描述：** 

- 获取接口凭证

**请求URL：** 
- `http://demo-wechat-platform.ibrand.cc/oauth/token`
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|client_id |是  |string | 客户凭证ID [生成客户凭证](/docs/{{type}}/{{version}}/client) |
|client_secret |是  |string |  同上 |




 **返回示例**

``` 
{
    "token_type": "Bearer",
    "access_token": "eyJ0eXAiOiJKVLitqTIUn8Y2DAQRH37uI_RaRCofG2f5ifYPdTiyKtb4fwcWGxpo8Dc9ULg-18t-x-8RuQL8BMgvshfzgv2CNN4RU63yw1fula17MoHSQaz-Bg2idRR_y10jCMQiju7kjZWk-Oz0j12WK5VBPxSG8PvaNgQFh9w8W7Hxngaa6t_QwRAAUGHea9L1vqpUBnS-rtbEmpX_-vRSEXr9vgYGLG_7WCW8reBQZ5r9gm5RGZ5yc78NwDc1C_Ynj0Dt0hlC-QVD9uRsP-FOXKz77HOlRIaqAD0GxgIHew13YWcJfJi79R7cSSQATlHxI7J0DtjmOOkvuXm1rifpquIq9qC1W8cAQBUiEPx4-cQ3sijfMF1h6eSG3pPbXwUiV3wbbHq2yqlJfjOzJTWhn1O6JcjIKD4UlwkkbwlNunAkpHNg6clfehyW2qJ8tlLMxGHXX7_xQM8na505KwqUSFnp6iOznKsKyFz6aRqe9PuOtZXVgIsxJUdQZAuGVDc",
    "expires_in": 864000
}
```

 ****  



