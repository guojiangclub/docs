# 分销模块数据字典

### 表名称：ibrand_agent 分销员

| 字段             | 类型                   | 空   | 索引 | 默认值 | 注释                                              |
| ---------------- | ---------------------- | ---- | ---- | ------ | ------------------------------------------------- |
| id               | INT(10) 自增长、无符号 | 否   | 主键 |        |                                                   |
| user_id          | INT(11)、无符号        | 否   |      |        | 用户ID                                            |
| name             | VARCHAR(255)           | 否   |      |        | 姓名                                              |
| mobile           | VARCHAR(255)           | 否   |      |        | 手机号码                                          |
| note             | VARCHAR(255)           | 是   |      | NULL   | 备注                                              |
| code             | VARCHAR(255)           | 否   | 唯一 |        | 编码                                              |
| status           | TINYINT(4)、无符号     | 否   |      | 0      | 状态 0：待审核  1：审核通过 2：审核不通过 3：清退 |
| total_commission | INT(11)、无符号        | 否   |      | 0      | total_commission                                  |
| balance          | INT(11)、无符号        | 否   |      | 0      | 佣金余额                                          |
| type             | TINYINT(4)、无符号     | 否   |      | 1      | 分销员类型：1 普通 2 机构 3 门店                  |
| created_at       | TIMESTAMP              | 是   |      | NULL   |                                                   |
| updated_at       | TIMESTAMP              | 是   |      | NULL   |                                                   |
| deleted_at       | TIMESTAMP              | 是   |      | NULL   |                                                   |

------

### 表名称：ibrand_agent_relation 分销员关系

| 字段            | 类型                   | 空   | 索引 | 默认值 | 注释           |
| --------------- | ---------------------- | ---- | ---- | ------ | -------------- |
| id              | INT(10) 自增长、无符号 | 否   | 主键 |        |                |
| level           | INT(11)、无符号        | 否   |      |        | 相对等级       |
| parent_agent_id | INT(11)、无符号        | 否   |      |        | agent_id的父ID |
| agent_id        | INT(11)、无符号        | 否   |      |        | 分销商ID       |
| created_at      | TIMESTAMP              | 是   |      | NULL   |                |
| updated_at      | TIMESTAMP              | 是   |      | NULL   |                |
| deleted_at      | TIMESTAMP              | 是   |      | NULL   |                |

------

#### 表名称：ibrand_agent_user_relation 分销员用户关系

| 字段       | 类型                   | 空   | 索引 | 默认值 | 注释                    |
| ---------- | ---------------------- | ---- | ---- | ------ | ----------------------- |
| id         | INT(10) 自增长、无符号 | 否   | 主键 |        |                         |
| agent_id   | INT(11)、无符号        | 否   |      |        | 分销商ID                |
| user_id    | INT(11)、无符号        | 否   |      |        | 用户ID                  |
| flag       | TINYINT(4)、无符号     | 否   |      | 2      | 是否是新用户：1 是  2否 |
| created_at | TIMESTAMP              | 是   |      | NULL   |                         |
| updated_at | TIMESTAMP              | 是   |      | NULL   |                         |
| deleted_at | TIMESTAMP              | 是   |      | NULL   |                         |

------

#### 表名称：ibrand_agent_cash 分销员提现记录

| 字段        | 类型                   | 空   | 索引 | 默认值 | 注释                                                     |
| ----------- | ---------------------- | ---- | ---- | ------ | -------------------------------------------------------- |
| id          | INT(10) 自增长、无符号 | 否   | 主键 |        |                                                          |
| agent_id    | INT(11)、无符号        | 否   |      |        | 分销商ID                                                 |
| amount      | INT(11)、无符号        | 否   |      | 0      | 金额                                                     |
| balance     | INT(11)、无符号        | 否   |      | 0      | 余额                                                     |
| status      | TINYINT(4)、无符号     | 否   |      | 0      | 状态 0：待审核  1:待打款提现 2：已打款提现  3:审核不通过 |
| settle_time | DATETIME               | 是   |      | NULL   | 打款时间                                                 |
| created_at  | TIMESTAMP              | 是   |      | NULL   |                                                          |
| updated_at  | TIMESTAMP              | 是   |      | NULL   |                                                          |
| deleted_at  | TIMESTAMP              | 是   |      | NULL   |                                                          |