 # 优惠券列表
 
 ****
     
**简要描述：** 

优惠券列表展示 

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/coupon?type={值} `
  
**请求方式：**
- GET 

**参数：**


|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|type |是  |string | 是否有效  invalid 无效 valid 有效  used 获取已使用优惠券|

 **返回示例**

``` 
  {
  "data": [
    {
      "id": 2,
      "discount_id": 2,
      "user_id": 1,
      "code": "211",
      "used_at": "2016-10-10 16:54:27",
      "discount": {
        "id": 2,
        "title": "1123",
        "label": "123",
        "intro": null,
        "exclusive": 0,
        "usage_limit": 6,
        "used": 16,
        "code": "111",
        "type": 0,
        "coupon_based": 1,
        "starts_at": "2016-10-11 16:59:27",
        "ends_at": "2016-11-02 16:59:31",
        "status": 1,
        "created_at": null,
        "updated_at": "2016-10-12 13:23:03",
        "deleted_at": null,
       "rules": [
        {
          "id": 63,
          "discount_id": 48,
          "type": "contains_category",
          "configuration": "{\"items\":[41,1,47,60,68]}"
        },
        {
          "id": 72,
          "discount_id": 48,
          "type": "contains_category",
          "configuration": "{\"items\":[28,84,70,44,10]}"
        },
        {
          "id": 77,
          "discount_id": 48,
          "type": "item_total",
          "configuration": "{\"amount\":66214}"
        },
        {
          "id": 78,
          "discount_id": 48,
          "type": "item_total",
          "configuration": "{\"amount\":52537}"
        },
        {
          "id": 79,
          "discount_id": 48,
          "type": "cart_quantity",
          "configuration": "{\"count\":5}"
        }
      ],
       "actions": [
        {
          "id": 44,
          "discount_id": 48,
          "type": "order_percentage_discount",
          "configuration": "{\"percentage\":9}"
        }
      ]
      },
      "expires_at": "",
      "created_at": "",
      "updated_at": "",
      "deleted_at": ""
    }
  ],
  "meta": {
    "pagination": {
      "total": 21,
      "count": 15,
      "per_page": 15,
      "current_page": 1,
      "total_pages": 2,
      "links": {
        "next": "http://dev.dmp2016.com/api/coupon?page=2"
      }
    }
  }
}
```

**返回值说明：**

**基础信息**

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|code |是  |string | 该优惠券的唯一编码|
|expires_at |是  |datetime | 过期时间|
|used_at |是  |datetime | 使用时间|

**discount 信息**

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|coupon_based |是  |bool | discount 该值为1 表示是一个优惠券|
|title |是  |string | 优惠券名称|
|label |是  |string | 满100减50，可读性简短描述|
|intro |是  |string | 优惠券的详细描述|
|exclusive |是  |bool | 是否排他，暂未使用|
|usage_limit |是  |int | 使用限制，如果未空，表示不限制。|
|used |是  |int | 已使用|
|code |是  |string | discount 的编码|
|type |是  |int | 值待定，可能改为英文可读|
|starts_at |是  |datetime | 开始时间|
|ends_at |是  |datetime | 结束时间|
|status |是  |int | 待完善|

**rules 规则**

一个促销或者优惠券可以包含多个应用条件，只有满足这些条件的时候才可使用

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|type |是  |string | contains_category（包含指定分类） contains_product（包含指定产品）  cart_quantity（购物车数量或者订单数量）   item_total（订单中购物车中商品本身的销售金额总数） |
|configuration |是  |string | 规则限制 |

**actions 动作**

一个促销中可以应用多个优惠动作，但是现在系统中一般只会配置一个。所以返回值仍然是数组形式，请注意。

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|type |是  |string | order_fixed_discount（订单直接减金额） order_percentage_discount（订单直接打折）  unit_fixed_discount（订单中商品减金额）   item_total（订单中商品打折） |
|configuration |是  |string | 一般就两种值：amount，percentage |


