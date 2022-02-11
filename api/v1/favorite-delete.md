 # 取消收藏
 
 ****
     
**简要描述：** 

- 删除收藏

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/favorite`
  
**请求方式：**
- DELETE 

- 登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|favoriteable_id |是  |string |ID(如果是商品收藏则是商品ID)   |
|favoriteable_type |是  |string | 类型(如 goods，story)    |


 **返回示例**

``` 
  {
  "status": true,
  "code": 200,
  "message": "",
  "data": ""
}
```

