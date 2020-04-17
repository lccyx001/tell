# 数据库表结构设计

- 用户

| 字段        | 类型        | 备注     |
|-------------|-------------|----------|
| id          | int         | 自增主键 |
| name        | varchar(12) | 姓名     |
| password    | varchar(12) | 密码     |
| cookie      | json        | json     |
| create_time | datetime    |          |
| update_time | datetime    |          |

- 聊天室

| 字段        | 类型        | 备注         |
|-------------|-------------|--------------|
| id          | int         | 自增主键     |
| name        | varchar(20) | 聊天室名称   |
| max_limit   | int         | 最大人数限制 |
| total       | int         | 当前人数     |
| create_time | datetime    |              |
| update_time | datetime    |              |

- 消息记录

| 字段        | 类型     | 备注     |
|-------------|----------|----------|
| id          | int      | 自增主键 |
| message     | text     | 消息内容 |
| from_site   | int      | 用户id   |
| to_site     | int      | 用户id   |
| channge_id  | int      | 聊天室id |
| id          | int      | 自增主键 |
| create_time | datetime |          |
