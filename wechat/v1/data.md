
#数据统计与分析
 ****

**简要描述：**


- 数据统计与分析


**路由：**

```
http://demo-wechat-platform.ibrand.cc/api/data/{str}?appid={appid}

```
**请求方式：**
- GET

**参数：**


|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|appid |是  |string |  |
|form |是  |string |   示例： `2018-02-13`|
|to |是  |string | 示例： `2018-02-13` |

 ****
 
```
http://demo-wechat-platform.ibrand.cc/api/data/userSummary?appid={appid} 
获取用户增减数据, 最大时间跨度：7;

http://demo-wechat-platform.ibrand.cc/api/data/userCumulate?appid={appid} 
获取累计用户数据, 最大时间跨度：7;

http://demo-wechat-platform.ibrand.cc/api/data/articleSummary?appid={appid} 
获取图文群发每日数据, 最大时间跨度：1;


http://demo-wechat-platform.ibrand.cc/api/data/articleTotal?appid={appid} 
获取图文群发总数据, 最大时间跨度：1;

http://demo-wechat-platform.ibrand.cc/api/data/userReadSummary?appid={appid} 
获取图文统计数据, 最大时间跨度：3;


http://demo-wechat-platform.ibrand.cc/api/data/userReadHourly?appid={appid} 
获取图文统计分时数据, 最大时间跨度：1;


http://demo-wechat-platform.ibrand.cc/api/data/userShareSummary?appid={appid} 
获取图文分享转发数据, 最大时间跨度：7;

http://demo-wechat-platform.ibrand.cc/api/data/userShareHourly?appid={appid} 
获取图文分享转发分时数据, 最大时间跨度：1;

http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageSummary?appid={appid} 
获取消息发送概况数据, 最大时间跨度：7;

http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageHourly?appid={appid} 
获取消息发送分时数据, 最大时间跨度：1;

http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageWeekly?appid={appid} 
获取消息发送周数据, 最大时间跨度：30;

http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageMonthly?appid={appid} 
获取消息发送月数据, 最大时间跨度：30;

http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageDistSummary?appid={appid} 
获取消息发送分布数据, 最大时间跨度：15;

http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageDistWeekly?appid={appid} 
获取消息发送分布周数据, 最大时间跨度：30;


http://demo-wechat-platform.ibrand.cc/api/data/upstreamMessageDistMonthly?appid={appid} 
获取消息发送分布月数据, 最大时间跨度：30;

http://demo-wechat-platform.ibrand.cc/api/data/interfaceSummary?appid={appid} 
 获取接口分析数据, 最大时间跨度：30;

http://demo-wechat-platform.ibrand.cc/api/data/interfaceSummaryHourly?appid={appid} 
获取接口分析分时数据, 最大时间跨度：1;


```
 ****



