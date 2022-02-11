 # 批量删除收藏
 
 ****
     
**简要描述：** 

- 我的收藏 批量删除操作

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/favorite/delFavs `
  
**请求方式：**
- POST 

- 登陆后才可请求，需 [认证参数](https://www.ibrand.cc/docs/api/v1/authentication "认证参数")


**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|ids |是  |array |ids[]=1   |



 **返回失败示例**

``` 
  {
  "status": false,
  "code": 400,
  "message": "删除失败",
  "data": ""
}
```

 **返回示例**

``` 
  {
  "status": true,
  "code": 200,
  "message": "",
  "data": ""
}
```

