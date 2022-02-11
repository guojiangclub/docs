 
# 接口验证参数
****
    
**简要描述**

调用相关接口，必须凭票据访问。需要通过通过 `http headers` 传递 `Authorization` 参数。


**认证参数：**

请求 Headers 添加如下参数：

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|Authorization |是  |string |Bearer+空格+用户登录后获取到的 access_token 。如：Bearer sdfsdfsdfsfsdfsf123  |
|Accept |否  |string | application/json    |


****