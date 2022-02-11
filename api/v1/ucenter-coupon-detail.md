 # 优惠券详情
 
 ****
     
**简要描述：** 

获取优惠券详细

**请求URL：** 
- `https://demo-open-admin.ibrand.cc/api/coupon/{id} `
  
**请求方式：**
- GET 


 **返回示例**

``` 
 {
  "status": true,
  "code": 200,
  "message": "",
  "data": [
    {
      "id": 1,
      "discount_id": 1,
      "user_id": 1,
      "code": "55",
      "used_at": null,
      "expires_at": null,
      "created_at": null,
      "updated_at": null,
      "deleted_at": null,
      "discount": {
        "id": 1,
        "title": "1",
        "label": "111",
        "intro": null,
        "exclusive": 0,
        "usage_limit": 1,
        "used": 1,
        "code": null,
        "type": 0,
        "coupon_based": 1,
        "starts_at": "2016-10-02 16:50:07",
        "ends_at": "2016-10-26 16:50:11",
        "status": 1,
        "created_at": null,
        "updated_at": null,
        "deleted_at": null,
        "rules": [],
        "actions": []
      }
    }
  ]
}
```

