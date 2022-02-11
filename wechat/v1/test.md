  
# test
****    
    
**简要描述：** 

- access_token 是前端自定义的一串随机字符串，开发环境下不真实发送短信，请使用 http://dmp2016.chenhow.com/api/sms/info?access_token= XXX 查看当前已发送的短信。

**请求URL：** 
- `http://dmp2016.chenhow.com/api/sms/verify-code`
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|mobile |是  |string |手机号   |
|access_token |是  |string |请前端自定义一段字符串传送过去，验证短信时需要附带此参数和值   |
|interval |否  |int |请求间隔秒数，不设置则默认60秒   |
|template_id |否  |string | 各类渠道的模板id，阿里大鱼等支持。  |



 **返回示例**

``` 
 {
  "success": true,
  "type": "sms_sent_success",
  "message": "短信验证码发送成功，请注意查收"
}
```

**失败示例**

``` 
{
  "success": false,
  "type": "request_invalid",
  "message": "请求无效，请在60秒后重试"
}
```





 **说明** 

|参数名|类型|说明|
|:-----  |:-----|-----|
|500 |int | 服务器的内部错误  |
|405|int| 不允许此方法|
|404|int| Web 服务器找不到您所请求的文件或脚本|
|403|int| 禁止访问 |
|401|int| 未授权 |
|400|int| Web 请求出错, 检测下url请求|



 **备注** 
 
  **** 



