#### 负责人
唐期

#### 重要备注
1. 性能问题。
2. 队列。

#### 功能说明

“定向发券”通过会员卡、加入购物车、购买次数、买过的商品、注册手机号等各种用户属性和历史行为，筛选出目标用户，并给这些用户定向群发优惠券，达到精准营销的目的。

##### 主要操作界面和功能说明：
1. 进入后台定向发券列表，点击定向发券模块的“立即创建”，进入新建定向发券界面；
2. 创建定向发券分四大步骤：选人群、设优惠券、设置发放人数、添加活动名称；
3. 根据选择的人群条件，系统自动计算可以发放人数，允许手动调整发放人数，当优惠券库存不足时，券发完为止；
4. 群发优惠券直接发到用户帐号，不需要用户再点击领取；
5. 单次最大支持给5000人群发优惠券；
6. 因为群发需要一定时间，可以在定向发券列表查看投放人数、发券进度、成功发放数；

注意：
1. 因为微信对优惠券类群发的消息推送限制，给主动客户发券后，目前只支持对绑定手机号的用户进行短信通知，是否短信通知可选；
2. 群发操作不可撤回，群发前务必检查好人群、优惠券等关键设置项；
3. 群发受各种因素影响，跟短信群发、邮件群发类似，群发成功率不一定能达到100%；

![image](https://bbs-img.yzcdn.cn/forum/201704/17/102906ciiz1hhvgzppm9yx.png!ori)

![image](https://bbs-img.yzcdn.cn/forum/201704/20/112038uee2vwf22138g3y1.png!ori)

##### 注册手机号：
是指客户在有赞注册时候的手机号，一次最多支持80个手机号，多个手机号用逗号分隔，目前仅支持中国大陆的手机号，需要添加“+86”信息；

![image](https://bbs-img.yzcdn.cn/forum/201704/20/112722qzngqbgebqi9y8qq.png!ori)

##### 自定义人群：

当选择的是自定义人群，支持多个自定义条件时叠加的，比如，当N天内有购买选择90，N天内无购买选择30，对应的人群就是“90天内有购买，且30天内无购买”的这批人

![image](https://bbs-img.yzcdn.cn/forum/201704/17/105641uz772ii9urzs7su7.png!ori)

创建定向发券活动时，可以设置短信通知客户：
批量发券完成，给成功发到券，且有注册手机号的客户推送短信消息；
如果剩余短信数少于发券人数，会提示充值，如果短信不充值仍可以群发优惠券，但是短信发完后，剩余的其他人将无法收到短信通知；