  
 # 短信登录
 
 ****   
    
**简要描述：** 

- 验证成功后，系统不存在该手机用户，则会生成新的用户

> 开发模式下，不会验证验证码的有效性，可以使用任意字符传给后端

**请求URL：** 

- `https://demo-open-admin.ibrand.cc/api/oauth/sms `
  
**请求方式：**
- POST 

**参数：** 

- 普通登陆

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|mobile |是  |string | 手机号   |
|code |是  |string | 验证码    |
|open_id | 否  |string | 小程序用户 openid    |

 
 **返回示例**

```json
{
  "token_type": "Bearer",
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6IjdkMDFjMGI0ZDRmODhjYTEwYjA3MDI0ZWEzYTU1MTc5MTQ4Y2NkNTZjZGIwMDEyMGFjNjA5MTIzNGYyNDUxZTAzZjdlNjFlOTkwN2MzYjQ0In0.eyJhdWQiOiIxIiwianRpIjoiN2QwMWMwYjRkNGY4OGNhMTBiMDcwMjRlYTNhNTUxNzkxNDhjY2Q1NmNkYjAwMTIwYWM2MDkxMjM0ZjI0NTFlMDNmN2U2MWU5OTA3YzNiNDQiLCJpYXQiOjE0NzQ4NzQ0OTksIm5iZiI6MTQ3NDg3NDQ5OSwiZXhwIjo0NjMwNTQ4MDk5LCJzdWIiOiIxIiwic2NvcGVzIjpbXX0.jSbK7tetZohQS397315_Aw_ZdQ16kFzE-wIGkC9Ufg9MOnFDZnvqvlSQzRWWgkr_dRjj732AGyoj9lyag-ylgjCBZxXEtGUBKUlK_Pt32B9BQCloiTzp8M081J3VMRuFTy9hCym-xiGK_huM8rN_jZnfN4NJ0ILnr8Na8e2ozNAOX5xe9OCegfCdrpUv0OYzLScRS4E7yA53zyWxCRWQrIY0eqWwRnOkpMqGVYdEPpCd9FBdS0uOH4g0IIefLMEbFgAbwYQ52j2gaKuuOO-la9fqMK7_1aje_nlhJsFg-488_8KstPFQppvLcP1cznHew5ejd1IqJm0fLkVG0pw13v67jg0ds4kV0b3z9pfFE5Z3UkhThEkXh1q0EbwdS3HTyEUoAzaSxqx-cZn1zm2mgzk39U6yt9NwbmMDBUIq0rA4LI64oqUT_vExCiBDf0isvhHCzwql9OGv422cLTDN7pv77oqU-zc0AIM41IwqqNvyKXrazYHN2D7Appjjc0ajg7IWspAyMZmFjHMohRSzN253dS96HIjuyu_vYTTbfT0G9SdGY2kLKrSZo4-PUZi9tM6ecYdrKLYXMfUs8NC_iWXjqTyEOTwGMKa5tfWniPuKzcdoFeMe0zOsHGy5NSrs5O-zZZWwup-q1vNAuuFvCqcwDuW6TumcGKK3oEWZVBs"
}

```




