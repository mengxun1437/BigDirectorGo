# 我是大导演

项目 -> 环节

project -> process





## 用户 `/user`

注册用户  PUT

```json
{
    "openid": "123456",
    "username": "asdf",
    "qqnum": "150521321",
    "avatar":"asdfasdfsa",
   	"phonenum":"13456"
}
```



获取用户信息  GET

示例：GET `/user/123456`

结果：

```json
{
    "data": {
        "openid": "123456",
        "username": "asdf",
        "phonenum": "13456",
        "avatar": "asdfdlfajsldfjsaldkf",
        "qqnum": "150521321",
        "CreatedAt": "2020-05-16T21:30:44+08:00",
        "UpdatedAt": "2020-05-16T21:55:52+08:00",
        "DeletedAt": null
    },
    "error": 0,
    "msg": "success"
}
```



修改用户信息 PATCH

示例：PATCH`/user/123456`

```json
{
    "openid": "123456",
    "username": "asdf",
    "qqnum": "150521321",
    "phonenum": "13456",
    "avatar": "asdfdlfajsldfjsaldkf"
}
```

结果：

```json
{
    "data": {
        "openid": "123456",
        "username": "asdf",
        "phonenum": "13456",
        "avatar": "11111",
        "qqnum": "150521321",
        /*无效数据
        "CreatedAt": "0001-01-01T00:00:00Z",
        "UpdatedAt": "0001-01-01T00:00:00Z",
        "DeletedAt": null
        */
    },
    "error": 0,
    "msg": "success"
}
```



获取用户参与的项目 GET `/project





| error |    msg     |                 报错原因                 |
| :---: | :--------: | :--------------------------------------: |
| 40301 |  json错误  | json的格式或者数据不对，比如说必选项为空 |
| 40400 | none user  |          用户id没找到对应的账户          |
| 50000 |  插入错误  |      数据库问题或者有主键重复等错误      |
| 40302 |  json错误  |                 同40301                  |
| 40303 | openid错误 |         地址栏id和json id不一致          |
| 40401 | none user  |                 同40400                  |
| 50001 |  更新错误  |                 详见msg                  |



## 项目 `/project`

新建项目 PUT

获取项目详情 GET

- 项目id
- 项目名
- 项目创建日期
- 项目导演姓名
- 项目中人员总个数(含导演)、负责人个数(不含导演)、和非负责人个数
- 项目的环节

修改项目信息 PATCH

获取项目的所有成员 GET `/user`

- 标识用户的权限

新建负责人 PUT







## 环节 `/process`

新建环节 PUT

获取环节详情 GET

修改环节信息 PATCH

新建环节负责人 PUT