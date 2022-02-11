# 秒杀功能文档

### 开发人员
彭磊，唐维，姚超

### 功能说明
#### 秒杀列表
1.显示参与秒杀的商品列表，不管秒杀活动有没有开始，按照秒杀开始时间排序，点击可跳转到对应的商品详情页。

2.秒杀开始则显示秒杀还剩多久结束的时间的倒计时

3.秒杀未开始则显示秒杀还剩多久开始的倒计时。

4.如果秒杀开始时间与现在时间间隔超过一天以上则显示X月X日，xx:xx开始。

5.秒杀商品不再支持细化到SKU,只到SPU层面。针对SPU设置秒杀价。

#### 商品详情
1.商品参与秒杀但是活动未开始，购买按钮显示为原价购买。

2.商品参与秒杀并且活动开始，购买按钮显示为立即抢购。

3.如果服务器拥挤导致不能下单则弹出一个倒计时为10秒的弹窗。

4.秒杀不走购物车流程，直接进入到订单结算页面。

### 图示
![image](http://oscbwf6by.bkt.clouddn.com/U1EAMJZ%293$S3%29%7D%5DH~OMX%25H8.png) (秒杀列表)

![image](http://oscbwf6by.bkt.clouddn.com/29TA3$DOVDBLH5C%7B%7DV%259W37.png)(未开始1)
![image](http://oscbwf6by.bkt.clouddn.com/9CS%7B%25%281E%251OF6%5B51Q%5D%5DNZEN.png)(倒计时)
![image](http://oscbwf6by.bkt.clouddn.com/EWRG4ZW%288%28ZA9H7@8HS7CRG.png)(进行中)
### 开发说明
1.秒杀列表请求接口地址`api/seckill/all`

2.秒杀结算请求接口地址`api/shopping/order/checkout?seckill_item_id=`
参数为当前商品参与的秒杀活动id

3.判断秒杀是否已经开始
`item.init_status == 1`

4.判断秒杀是否未开始
`item.init_status == 2`

5.判断是否弹窗

```
// 当返回的status为false，并且data.server_busy值不为空才弹窗
checkout(status, res) {
    if (status) {
	    this.$router.forward({ name: 'store-order',query:{type:"seckill"}});
        } else {
            if (res.data && res.data.server_busy) {
            	this.show_ten = true   // 弹窗
                } else {
			     this.$Alert(res.message || '请求失败');
                }
        }
    }
```



