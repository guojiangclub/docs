
#数据统计与分析
 ****

**简要描述：**


- 数据统计与分析


**路由：**

```
http://demo-wechat-platform.ibrand.cc/api/mini/data/{str}?appid={appid}

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
http://demo-wechat-platform.ibrand.cc/api/mini/data/summaryTrend?appid={appid}         概况趋势;
http://demo-wechat-platform.ibrand.cc/api/mini/data/dailyVisitTrend?appid={appid}      访问日趋势;
http://demo-wechat-platform.ibrand.cc/api/mini/data/weeklyVisitTrend?appid={appid}     访问周趋势;

http://demo-wechat-platform.ibrand.cc/api/mini/data/monthlyVisitTrend?appid={appid}    访问月趋势;
http://demo-wechat-platform.ibrand.cc/api/mini/data/dailyRetainInfo?appid={appid}      访问日留存;
http://demo-wechat-platform.ibrand.cc/api/mini/data/weeklyRetainInfo?appid={appid}     访问周留存;


http://demo-wechat-platform.ibrand.cc/api/mini/data/monthlyRetainInfo?appid={appid}    访问月留存;
http://demo-wechat-platform.ibrand.cc/api/mini/data/visitPage?appid={appid}            访问页面;
http://demo-wechat-platform.ibrand.cc/api/mini/data/userPortrait?appid={appid}         用户画像分布数据;

```
 ****



