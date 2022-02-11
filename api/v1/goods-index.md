# 商品列表
 
 ****       
    
**简要描述：** 

- 获取商品列表接口，除返回商品数据外，还会附带分页数据以及筛选条件数据作为 meta 返回

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/store/list `
  
**请求方式：**
- GET  

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
| c_id |否  | int | 分类ID   |
| specs |否  | array|  specs[key]=value; 如 specs[color]=蓝色|
| attr   |否  |array |  attr[]=value; 如 attr[]=单日&attr[]=20升以下    |
| page |否  | int | 页码   |
| orderBy |否  | string | 排序的字段名称，不传默认为 商品上架日期   |
| sort |否  | string | asc 或者 desc ,不传默认为 desc   |
| keyword |否  | string | 搜索关键词，根据商品名称模糊匹配   |
| brand_id |否  | int | 品牌ID   |
| price |否  | string | 价区间，请以英文"-"符号链接。如： 0-499   |

 **返回示例**

``` 
{
    "status": true,
    "data": [
        {
            "id": 114,
            "name": "【驱蚊神器】创意卡通驱蚊扣10块3个颜色随机发",
            "goods_no": "2018672",
            "brand_id": 18,
            "model_id": 11,
            "min_price": "10.00",
            "max_price": "10.00",
            "sell_price": "10.00",
            "market_price": "28.80",
            "min_market_price": "28.80",
            "store_nums": 298,
            "img": "https://cdn.viperky.com/storage/images/20180607/IREjBpFLfp.png",
            "sync": 0,
            "comment_count": 18,
            "visit_count": 0,
            "favorite_count": 0,
            "sale_count": 2,
            "grade": 90,
            "tags": [],
            "keywords": "",
            "description": "",
            "is_del": 0,
            "is_largess": 0,
            "is_commend": 0,
            "is_new": 0,
            "extra": "{\"video\":{\"status\":\"0\",\"url\":\"\"}}",
            "created_at": "2018-06-07 14:50:10",
            "updated_at": "2018-06-26 15:32:55",
            "weight": "",
            "content": "",
            "contentpc": "",
            "collocation": "",
            "deleted_at": ""
        },
        {
            "id": 84,
            "name": "韩系范糖果色儿童防晒服可变背包",
            "goods_no": "17180",
            "brand_id": 9,
            "model_id": 9,
            "min_price": "59.00",
            "max_price": "59.00",
            "sell_price": "59.00",
            "market_price": "118.00",
            "min_market_price": "118.00",
            "store_nums": 1000,
            "img": "https://cdn.viperky.com/storage/images/20180521/YvhTF5FavK.png",
            "sync": 0,
            "comment_count": 6,
            "visit_count": 0,
            "favorite_count": 0,
            "sale_count": 11,
            "grade": 30,
            "tags": [],
            "keywords": "",
            "description": "",
            "is_del": 0,
            "is_largess": 0,
            "is_commend": 0,
            "is_new": 0,
            "extra": "{\"video\":{\"status\":\"0\",\"url\":\"\"}}",
            "created_at": "2018-05-21 16:14:34",
            "updated_at": "2018-06-15 17:41:13",
            "weight": "",
            "content": "",
            "contentpc": "",
            "collocation": "",
            "deleted_at": ""
        }
    ],
    "meta": {
        "filter": [],
        "pagination": {
            "total": 78,
            "count": 2,
            "per_page": 2,
            "current_page": 1,
            "total_pages": 39,
            "links": {
                "next": "http://open.dmp.com/api/store/list?page=2"
            }
        }
    }
}
```