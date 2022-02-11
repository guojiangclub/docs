 # 修改资料
 
 ****
     
**简要描述：** 

修改用户相关信息，会根据 token 自动获取当前用户

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/users/update/info `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|  name  | 否 |string |  用户名称 |
|  nick_name  | 否 |string |  用户昵称 |
|  sex  | 否  |string| 性别：男女 |
|  birthday  | 否  |string| 生日 2016-08-12 |
|  city  |否  |string | 城市 |
|  education  | 否  |string| 受教育程度 |
|  qq  | 否  |string| QQ |
|  avatar  | 否  |string| 头像的 url |
|  email  | 否  |string| 邮箱 |
|  password  | 否  |string| 用户密码 |

 **返回示例**

``` 
 {
  "data": {
    "id": 1,
    "name": "梅建明",
    "mobile": "18973305743",
    "email": "admin@dmp.com",
    "status": 1,
    "confirmed": 0,
    "avatar": "http://dev.wildrampage.com/images/ucenter/no_head.png",
    "integral": 0,
    "available_integral": 0,
    "group_id": 1,
    "discount": "0.00",
    "city": "上海",
    "education": "",
    "birthday": "2016-08-12",
    "qq": "",
    "card_limit": "2016-08-04",
    "created_at": "2016-08-04 15:30:15",
    "updated_at": "2016-08-17 15:13:22",
    "last_login": "2016-08-12 15:19:08",
  }
}
```


