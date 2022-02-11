 # 商品库存
 
 ****  
     
**简要描述：** 

- 获取商品 SKU 详细信息及相关库存数据

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/store/detail/{goods_id}/stock `

说明： {goods_id}  为目前的商品ID
  
**请求方式：**
- POST 

**参数：** 

无


 **返回示例**

``` 
{
    "status": true,
    "code": 200,
    "data": {
        "specs": {
            "1": {
                "id": 2,
                "label_key": "color",
                "label": "颜色",
                "list": [
                    {
                        "id": 15,
                        "value": "孔雀蓝",
                        "spec_img": "https://cdn.viperky.com/storage/images/20180525/jLbHQsO1Pt.png",
                        "alias": "灰蓝"
                    },
                    {
                        "id": 46,
                        "value": "白色",
                        "spec_img": "https://cdn.viperky.com/storage/images/20180525/WDbdP5rafg.png",
                        "alias": "白色"
                    }
                ]
            },
            "2": {
                "id": 1,
                "label_key": "size",
                "label": "尺寸",
                "list": [
                    {
                        "id": 40,
                        "value": "90",
                        "spec_img": "",
                        "alias": "90"
                    },
                    {
                        "id": 41,
                        "value": "100",
                        "spec_img": "",
                        "alias": "100"
                    },
                    {
                        "id": 42,
                        "value": "110",
                        "spec_img": "",
                        "alias": "110"
                    },
                    {
                        "id": 43,
                        "value": "120",
                        "spec_img": "",
                        "alias": "120"
                    },
                    {
                        "id": 44,
                        "value": "130",
                        "spec_img": "",
                        "alias": "130"
                    }
                ]
            }
        },
        "stores": {
            "15-40": {
                "id": 959,
                "store": 5,
                "sku": "18172100373-1",
                "ids": [
                    "15",
                    "40"
                ]
            },
            "15-41": {
                "id": 960,
                "store": 5,
                "sku": "18172100373-2",
                "ids": [
                    "15",
                    "41"
                ]
            },
            "15-42": {
                "id": 961,
                "store": 5,
                "sku": "18172100373-3",
                "ids": [
                    "15",
                    "42"
                ]
            },
            "15-43": {
                "id": 962,
                "store": 5,
                "sku": "18172100373-4",
                "ids": [
                    "15",
                    "43"
                ]
            },
            "15-44": {
                "id": 963,
                "store": 5,
                "sku": "18172100373-5",
                "ids": [
                    "15",
                    "44"
                ]
            },
            "40-46": {
                "id": 964,
                "store": 5,
                "sku": "18172100373-6",
                "ids": [
                    "40",
                    "46"
                ]
            },
            "41-46": {
                "id": 965,
                "store": 5,
                "sku": "18172100373-7",
                "ids": [
                    "41",
                    "46"
                ]
            },
            "42-46": {
                "id": 966,
                "store": 5,
                "sku": "18172100373-8",
                "ids": [
                    "42",
                    "46"
                ]
            },
            "43-46": {
                "id": 967,
                "store": 5,
                "sku": "18172100373-9",
                "ids": [
                    "43",
                    "46"
                ]
            },
            "44-46": {
                "id": 968,
                "store": 5,
                "sku": "18172100373-10",
                "ids": [
                    "44",
                    "46"
                ]
            }
        }
    }
}
```




