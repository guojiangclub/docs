 # 商品详情页
 
 ****  
    
**简要描述：** 

- 商品详情API 接口，会返回以下和商品相关数据

- 1.商品自身的相关数据

- 2.商品的主图数据，见返回示例中的 `photos`

- 3.商品的SKU数据，见返回示例中的  `products`，默认只返回有库存的数据

- 4.商品的评论数据, 见返回示例中的 `comments`

- 5.商品的拓展属性数据，见返回示例中 `attributes`

**请求URL：** 
- ` https://demo-open-admin.ibrand.cc/api/store/detail/{id}`

**URL include 参数**

- `/detail/12?include=photos,products,oneComment`

-  请通过url 中的 include 参数来返回商品的关联数据
  
**请求方式：**
- GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是  |int |商品ID   |

 **返回示例**

``` 
{
    "status": true,
    "data": {
        "id": 100,
        "name": "本比小熊夏季宝宝背心2018新款休闲百搭夏装潮衣",
        "goods_no": "18172100373",
        "brand_id": 10,
        "model_id": 3,
        "min_price": "49.00",
        "max_price": "49.00",
        "sell_price": "49.00",
        "market_price": "75.00",
        "min_market_price": "75.00",
        "store_nums": 50,
        "img": "https://cdn.viperky.com/storage/images/20180525/fBOKr15rw6.png",
        "content": "<p><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071753374.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071491575.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071127561.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230071824219.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072775994.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072304864.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072522432.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230072842042.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073939546.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073467122.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073881449.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073516859.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230073910114.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074255636.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074464478.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074314989.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074443772.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><br style=\"color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255);\"/><img alt=\"undefined\" src=\"https://admin.viperky.com/storage/uploads/ueditor/php/upload/image/20180525/1527230074233151.jpg\" style=\"border: none; visibility: visible; vertical-align: bottom; max-width: 790px; color: rgb(51, 51, 51); font-family: &quot;Hiragino Sans GB&quot;, Tahoma, Arial, 宋体, sans-serif; font-size: 12px; text-align: center; white-space: normal; background-color: rgb(255, 255, 255); zoom: 1;\"/></p>",
        "sync": 0,
        "comment_count": 0,
        "visit_count": 0,
        "favorite_count": 0,
        "sale_count": 11,
        "grade": 0,
        "tags": [],
        "keywords": "",
        "description": "",
        "is_del": 0,
        "is_largess": 0,
        "is_commend": 0,
        "is_new": 0,
        "extra": "{\"video\":{\"status\":\"0\",\"url\":\"\"}}",
        "created_at": "2018-05-25 14:35:24",
        "updated_at": "2018-05-28 15:10:23",
        "weight": "",
        "contentpc": "",
        "collocation": "",
        "deleted_at": ""
    },
    "meta": {
        "attributes": null
    }
}
```




