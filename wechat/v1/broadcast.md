
# 群发发送消息
 ****

**简要描述：**


- 微信公众号群发发送消息


**路由：**

```
http://demo-wechat-platform.ibrand.cc/api/broadcast/send?appid={appid}

```
**请求方式：**
- POST

**参数：**

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|appid |是  |string |  |
|open_id |是  |array |  |
|type |是  |string |news, image,video,voice ,text,card_id|
|media_id |否  |string |类型为news, image,video,voice必填|
|text |否  |string |类型为text必填|
|card_id |否  |string |类型为card_id必填|

 ****



