 # 修改手机
 
 ****
     
**简要描述：** 

修改用户手机号接口,请先通过短信验证码发送获取验证码

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/users/update/mobile`
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| mobile | 是  | string | 手机号 |
| code | 是  |string | 手机验证码 |

 **返回示例**

``` 
{
  "data": {
    "id": 1,
    "email": "15116103402@163.com",
    "mobile": "15116103401",
    "status": 1,
    "confirmed": 0,
    "integral": 0,
    "available_integral": 0,
    "card_limit": "2016-10-09",
    "created_at": "2016-10-09 06:52:39",
    "updated_at": "2016-10-09 08:33:20",
    "group_id": 1,
    "name": "",
    "confirmation_code": "",
    "sex": "",
    "avatar": "",
    "discount": "",
    "city": "",
    "education": "",
    "birthday": "",
    "qq": "",
    "deleted_at": "",
    "group": {
      "data": {
        "id": 1,
        "name": "test",
        "grade": 0,
        "min": "",
        "max": "",
        "created_at": "",
        "updated_at": ""
      }
    }
  }
}
```

