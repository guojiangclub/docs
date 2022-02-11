  
 # 微信手机登录
 
 ****   
    
**简要描述：** 

- 微信小程序通过微信手机授权登录手机号来直接登录系统

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/oauth/MiniProgramMobileLogin`
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|code |是  |string | 微信code   |
|encryptedData |是  |string | 微信给的加密数据    |
|iv     |是  |string | 微信给的iv    |

 **返回示例**

``` 
{
  "token_type": "Bearer",
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6IjdkMDFjMGI0ZDRmODhjYTEwYjA3MDI0ZWEzYTU1MTc5MTQ4Y2NkNTZjZGIwMDEyMGFjNjA5MTIzNGYyNDUxZTAzZjdlNjFlOTkwN2MzYjQ0In0.eyJhdWQiOiIxIiwianRpIjoiN2QwMWMwYjRkNGY4OGNhMTBiMDcwMjRlYTNhNTUxNzkxNDhjY2Q1NmNkYjAwMTIwYWM2MDkxMjM0ZjI0NTFlMDNmN2U2MWU5OTA3YzNiNDQiLCJpYXQiOjE0NzQ4NzQ0OTksIm5iZiI6MTQ3NDg3NDQ5OSwiZXhwIjo0NjMwNTQ4MDk5LCJzdWIiOiIxIiwic2NvcGVzIjpbXX0.jSbK7tetZohQS397315_Aw_ZdQ16kFzE-wIGkC9Ufg9MOnFDZnvqvlSQzRWWgkr_dRjj732AGyoj9lyag-ylgjCBZxXEtGUBKUlK_Pt32B9BQCloiTzp8M081J3VMRuFTy9hCym-xiGK_huM8rN_jZnfN4NJ0ILnr8Na8e2ozNAOX5xe9OCegfCdrpUv0OYzLScRS4E7yA53zyWxCRWQrIY0eqWwRnOkpMqGVYdEPpCd9FBdS0uOH4g0IIefLMEbFgAbwYQ52j2gaKuuOO-la9fqMK7_1aje_nlhJsFg-488_8KstPFQppvLcP1cznHew5ejd1IqJm0fLkVG0pw13v67jg0ds4kV0b3z9pfFE5Z3UkhThEkXh1q0EbwdS3HTyEUoAzaSxqx-cZn1zm2mgzk39U6yt9NwbmMDBUIq0rA4LI64oqUT_vExCiBDf0isvhHCzwql9OGv422cLTDN7pv77oqU-zc0AIM41IwqqNvyKXrazYHN2D7Appjjc0ajg7IWspAyMZmFjHMohRSzN253dS96HIjuyu_vYTTbfT0G9SdGY2kLKrSZo4-PUZi9tM6ecYdrKLYXMfUs8NC_iWXjqTyEOTwGMKa5tfWniPuKzcdoFeMe0zOsHGy5NSrs5O-zZZWwup-q1vNAuuFvCqcwDuW6TumcGKK3oEWZVBs"
}
```



