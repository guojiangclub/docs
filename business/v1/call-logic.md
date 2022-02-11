
## 功能描述
1. 活动开始后，才能够在商品详情页显示 "集call" 的标志
2. 活动结束时间到期后，“集call”标志消失
3. 只有在活动未结束时，同时免费领全部用完后，才显示“集call已领完”标志
4. 用户集call完成后，虽然活动到期7天内，用户任然显示“集call已领完”，可以继续领取商品。
5. 免费领取的商品，需要在选择SKU 的时候，明显标记，免费礼品，领取后无法调换货更换尺码。
6. 免费领取的商品无法进行售后。


## 表设计

### el_free

name | type | null | description
---|---|---|---
id | int| not null | primary key
title | string | not null | 免费领活动名称
label | string | null | 显示名称，如果不设置，则默认去取商品、课程的名称
img | string | not null | 封面大图，必须设置，不从商品、课程等外部资源去读取。
status| int | not null | 状态： 0 待发布   1 有效   2 过期
limit | int | not null | 活动限额数量
per_count | int | not null | 每个任务的数量
starts_at | timestamp | not null | 活动开始时间
ends_at | timestamp | not null | 活动结束时间，活动结束后，就不能够在继续集call
freeable_id | int | not null | 免费领物品id，goods_id,course_id etc.
freeable_type| string | not null | 免费领物品类型 
created_at |  timestapm |  not null |
updated_at |  timestapm |  not null |

### el_free_task

name | type | null | description
---|---|---|---
id | int| not null | primary key
free_id |int |not null|
user_id |int |not null|
img     |strig|null|
status | int| 0 未完成  1已完成
created_at |  timestapm |  not null |
updated_at |  timestapm |  not null |

### el_free_task_item

name | type | null | description
---|---|---|---
id | int| not null | primary key
task_id |int |not null| 任务id
user_id |int |not null| 打call用户id
meta    |text|null| json 数据，存放用户的头像，用户等基础信息
created_at |  timestapm |  not null |
updated_at |  timestapm |  not null |


