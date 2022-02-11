
#修改图文素材
 ****

**简要描述：**


- 微信公众号素材修改图文素材



**路由：**

```
http://demo-wechat-platform.ibrand.cc/api/medias/update/article?appid={appid}

```
**请求方式：**
- POST

**参数：**

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|appid |是  |string |  |
|mediaId |是  |string |  |
|data |是  | array |包含title, thumb_media_id，author，digest 等具体参考微信文档 |
|index |是  |string |  |

详细参数请参考微信文档

 ****




