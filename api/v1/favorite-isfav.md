 # 是否收藏
 
 ****
     
**简要描述：** 

是否已收藏

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/favorite/isfav?favoriteable_id={id}&favoriteable_type={type} `
  
**请求方式：**
- GET 

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
  "data": {
    "is_Fav": 0
  }
}
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|is_Fav |int   |0.未收藏 1.已收藏  |
