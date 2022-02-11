# 认证参数

**简要描述：** 

所有需要登录后才能操作的接口，需要通过通过 `http headers` 传递 `Authorization` 参数。

**认证参数：**

请求 Headers 添加如下参数：

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|Authorization |是  |string |Bearer+空格+用户登录后获取到的 access_token 。如：Bearer f4gfdjdsrf8432  |

**Postman**

> 待完善


