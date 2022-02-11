# 数据字典


## ibrand_coterie

圈子主表，主要存储圈子的一些主要信息。

添加索引：

- user_id

|字段      |类型        |空   |默认 |注释|
|:----    |:-------    |:--- |-- -|------      |
|id	      |int     |否	|	 |	           |
|user_id	|int |否	|	| 圈子创建用户ID,也就是圈主 id |
|name     |string |否	|    |	 名称	|
|description |text |是   |    |	 描述		 |
|avatar     |string |是   |    |  圈子头像 |
|member_count |int(11)     |否   | 0  | 成员数量 |
|content_count |int |否 | 0 | 主题总数 |
|recommend_count |int |否 | 0 | 精华数量 |
|ask_count |int |否 | 0 | 问答数量 |
|cost _type | string |否 |  | free 免费 charge 收费 |
|duration_type | string |否 | joined | joined：加入后一年，deadline 固定期限截止日。 deadline 第一版功能先不提供 |
|recommend_at | timestamp |是 | NULL | 圈子被推荐时间 |
|price |int |否 | 0 | 入圈价格，单位分，0 表示免费 |
|notice |text | 是 |  | 付费须知，待定，可能这个字段不需要。 |
|created_at |timestamp |是 | | Laravel时间戳， 圈子创建时间 |
|updated_at |timestamp |是 | | Laravel时间戳 |
|client_id |string |是 | | null 表示的是私有部署，不为空表示公有云 |


## ibrand_coterie_member

圈子费用表，主要存储圈子的价格，促销活动等体系

添加索引：

- coterie_id

|字段      |类型        |空   |默认 |注释|
|:----    |:-------    |:--- |-- -|------      |
|id	      |int     |否	|	 |	           |
|coterie_id	|int |否	|	| 圈子ID |
|user_id     |int |否	|    |	会员id	|
|user_type |string |否   | normal |	owner:圈主  guest:嘉宾  normal:普通会员	|
| user_meta    | text      | 是   |        | 存储用户头像，昵称等                    |
| joined_at    | timestamp | 否   |        | 加入时间                                |
| is_forbidden | bool      | 否   | 0     | 是否禁言，1 为禁言，默认为0，不禁言     |
|created_at |timestamp |是 | | Laravel时间戳 |
|updated_at |timestamp |是 | | Laravel时间戳 |
|deleted_at |timestamp | | |  |

## ibrand_coterie_order

圈子订单表，存储圈子的订单付费信息，当用户没点击一次付费，发起支付时创建该条信息

添加索引：

- order_no,coterie_id,user_id 的聚合索引

|字段      |类型        |空   |默认 |注释|
|:----    |:-------    |:--- |-- -|------      |
|id	      |int     |否	|	 |	           |
|order_no	|string |否	|	| 订单编号 |
|coterie_id	|int |否	|	| 圈子ID |
|user_id     |int |否	|    |	会员id	|
|paid_at |timestamp |否   |  |	付费时间	|
| price    | int      | 否   | 0 | 付费金额                    |
|created_at |timestamp |是 | | Laravel时间戳 |
|updated_at |timestamp |是 | | Laravel时间戳 |
|deleted_at |timestamp | | |  |

## ibrand_coterie_content 

主题内容，用户在圈子内发布的内容

添加索引:

- user_id
- coterie_id

| 字段           | 类型      | 空   | 默认    | 注释                                                         |
| :------------- | --------- | ---- | ------- | :----------------------------------------------------------- |
| id             | int       | 否   |         | 主键                                                         |
| user_id        | int       | 否   | 0       | 用户id 0官方发布                                             |
| coterie_id     | int       | 否   | 0       | 圈子id                                                       |
| style_type     | string    | 否   | default | default:普通内容动态   question:问答型动态                   |
| cotent_type    | string    | 否   | default | default: 默认图文 link: 链接分享  file:文件分享，本期不实现文件分享内容 |
| description    | TEXT      | 否   |         | 描述,限制1000个字符以内。                                    |
| img_list       | TEXT      | 否   |         | 展示图片，限制9张图片，存放图片连接url                       |
| tags_list      | string    | 是   |         | 标签，每个主题内容限制3个标签                                |
| audio_list     | TEXT      | 是   |         | 音频文件集合                                                 |
| comment_count  | INT       | 否   | 0       | 评论数                                                       |
| praise_count   | INT       | 否   | 0       | 点赞数                                                       |
| status         | TINYINT   | 否   | 1       | 状态，后续考虑可能需要审核，第一阶段不审核，发布就直接展示。 |
| recommended_at | TIMESTAMP | 是   |         | 推荐时间，是否推荐请在 Model 中判断该字段是否有空，来返回一个 is_recommend  的 attribute |
| stick_at       | TIMESTAMP | 是   |         | 置顶时间，圈子中只有一个动态可以置顶                         |
| created_at     | TIMESTAMP | 是   | NULL    |                                                              |
| updated_at     | TIMESTAMP | 是   | NULL    |                                                              |
| deleted_at     | TIMESTAMP | 是   | NULL    |                                                              |
| client_id      | string    |      |         |                                                              |

## ibrand_coterie_content_comment

评论表：主要用于记录游记评论数据

添加索引：

- content_id

| 字段       | 类型      | 空   | 默认 | 注释                                 |
| ---------- | --------- | ---- | ---- | ------------------------------------ |
| id         | INT       | 否   |      | 主键                                 |
| user_id    | INT       | 否   |      | 用户id                               |
| content_id | INT       | 否   |      | 游记id                               |
| content    | TEXT      | 否   |      | 评论内容                             |
| meta       | TEXT      | 是   |      | 用户数据                             |
| status     | TINYINT   | 否   | 1    | 审核状态,0 待审核，1审核通过直接展示 |
| created_at | TIMESTAMP | 是   | NULL |                                      |
| updated_at | TIMESTAMP | 是   | NULL |                                      |

## ibrand_coterie_content_reply

评论回复表

添加索引：

- content_id
- comment_id

| 字段       | 类型      | 空   | 默认 | 注释                                 |
| ---------- | --------- | ---- | ---- | ------------------------------------ |
| id         | INT       | 否   |      | 主键                                 |
| user_id    | INT       | 否   |      | 用户id                               |
| content_id | INT       | 否   |      | 游记id                               |
| comment_id | INT       | 否   |      | 评论id                               |
| content    | TEXT      | 否   |      | 回复内容                             |
| meta       | TEXT      | 是   |      | 用户数据                             |
| status     | TINYINT   | 否   | 1    | 审核状态,0 待审核，1审核通过直接展示 |
| created_at | TIMESTAMP | 是   | NULL |                                      |
| updated_at | TIMESTAMP | 是   | NULL |                                      |

## ibrand_coterie_question

提问表

添加索引：

- content_id

| 字段           | 类型      | 空   | 默认 | 注释                                         |
| -------------- | --------- | ---- | ---- | -------------------------------------------- |
| id             | INT       | 否   |      | 主键                                         |
| content_id     | INT       | 是   |      | 关联的content_id，未回答问题前这个为字段为空 |
| user_id        | INT       | 否   |      | 提问用户 id                                  |
| answer_user_id | INT       | 否   |      | 被邀请回答的用户id                           |
| content        | text      | 否   |      | 提问的内容                                   |
| img_list       | text      | 是   |      | 提问的图片内容，提问只能上传图片             |
| created_at     | TIMESTAMP | 是   | NULL |                                              |
| updated_at     | TIMESTAMP | 是   | NULL |                                              |
| deleted_at     | TIMESTAMP | 是   |      |                                              |

## ibrand_coterie_content_praise

点赞表：主要用于记录游记点赞数据

添加索引：

- content_id

| 字段       | 类型      | 空   | 默认 | 注释     |
| ---------- | --------- | ---- | ---- | -------- |
| id         | INT       | 否   |      | 主键     |
| content_id | INT       | 否   |      | 游记id   |
| user_id    | INT       | 否   | 0    | 用户id   |
| meta       | TEXT      | 是   |      | 用户数据 |
| created_at | TIMESTAMP | 是   | NULL |          |
| updated_at | TIMESTAMP | 是   | NULL |          |
