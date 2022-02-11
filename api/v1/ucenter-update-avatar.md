# 上传头像
    
**简要描述：** 

上传用户头像，该方法只返回一个服务端图片地址，并不和相关用户进行关联保存 

**请求URL：** 
- ` https://demo-open-admin.ibrand.cc/api/users/upload/avatar`
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|avatar_file |是  |file | 用户选择的客户端图片   |
|Orientation |否  |int | 水平位置，可设置的值 3(逆时针180度),6(顺时针90度) ,8(逆时针90度)  |
|action |否  |string | 执行动作，默认不传，不会自动保存到用户上只会返回一个有效url。 可设置值为： save 表示直接保存到用户表头像字段  |


 **返回示例**

``` 
{
  "status": true,
  "code": 200,
  "message": "",
  "data": {
    "url": "http://dev.dmp2016.com/uploads/14zmaw2C64.png"
  }
}
```

 **备注** 

- 更多返回错误代码请看首页的错误代码描述


