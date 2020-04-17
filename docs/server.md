# 聊天室服务器设计

## 功能模块

- 用户登录/注册

- 用户信息查询

- 聊天室用户信息查询

- 消息收发

- 消息群发

## api 及 接口

响应信息统一结构

成功返回

```json
{
    "code":0,//0 success 其他 failed
    "msg":"success",
    // 如果有数据在data节点中，若没有，data节点不存在
    "data":{}
}
```

失败返回

```json
{
    "code":1,//错误码
    "msg":"错误信息"
}
```

### 用户登录

- url

```json
/login
```

- method

```json
post
```

- params

```json
{
    "name":"xxx",
    "password":"auth info"
}
```

- response

```json
{
    "token":"token xinxi"
}
```

### 用户注册

- url

```json
/register
```

- method

```json
post
```

- params

```json
{
    "name":"xxx",
    "password":"auth info",
    "password_repete":"auth info"
}
```

- response

```json
{


}
```

### 用户信息查询

- url

```json
/user/info
```

- method

```json
post
```

- params

```json
{
    "name":"xxx"
}
```

- response

```json
{
    "name":"xxx"
}
```

### 聊天室用户信息查询

- url

```json
/channel/list_users
```

- method

```json
post
```

- params

```json
{
    "name":"xxx",  //channel name
}
```

- response

```json
{
    "users":[
        {
            "name":"xxx"
        },{
            "name":"xxx"
        }
    ]
}
```

### 私信发送消息

- url

```json
/send
```

- method

```json
post
```

- params

```json
{
    "name":"xxx",  //to user name
    "msg":"hello"
}
```

### 私信接受消息

- url

```json
/receive
```

- method

```json
post
```

- params

```json
{
    "name":"xxx",  //用户 name
}
```

- response

```json
{
    "messages":{
        "user1":["msg1","msg2","msg3"],
        "user2":["msg1","msg2","msg3"],
    }
}
```

### 聊天室消息发送

- url

```json
/channel/send
```

- method

```json
post
```

- params

```json
{
    "name":"channel name",
    "message":"hello"
}
```

### 聊天室消息接受

- url

```json
/channel/receive
```

- method

```json
post
```

- params

```json
{
    "name":"channel name"
}
```

- response

```json
{
    "messages":[
        {
            "name":"user1",
            "datetime":"2020.03.05:12:12:00",
            "msg":"msg1"
            },
        {
            "name":"user1",
            "datetime":"2020.03.05:12:12:00",
            "msg":"msg1"
            },
        {
        "name":"user1",
        "datetime":"2020.03.05:12:12:00",
        "msg":"msg1"
            },
        {
        "name":"user1",
        "datetime":"2020.03.05:12:12:00",
        "msg":"msg1"
            },
    ]
}
```
