> MongoDB

# 基础

## 安装

> 省略

## 数据库操作

### 设置账号密码

> mongodb密码和传统数据如mysql等有些区别： mongodb的用户名和密码是基于特定数据库的，而不是基于整个系统的。所有所有数据库db都需要设置密码。

```
user:”用户名“，

pwd:"密码”，

roles：指定用户的角色，可以用一个空数组给新用户设定空角色；在roles字段,可以指定内置角色和用户定义的角色。

注: 帐号是跟着库走的，所以在指定库里授权，必须也在指定库里验证(auth)。
```

|  权限   | 解释  |
|  ----  | ----  |
| read  | 允许用户读取指定数据库 |
| readWrite  | 允许用户读写指定数据库 |
| dbAdmin  | 允许用户在指定数据库中执行管理函数，如索引创建、删除，查看统计或访问system.profile |
| userAdmin  | 允许用户向system.users集合写入，可以找指定数据库里创建、删除和管理用户 |
| clusterAdmin  | 只在admin数据库中可用，赋予用户所有分片和复制集相关函数的管理权限 |
| readAnyDatabase  | 只在admin数据库中可用，赋予用户所有数据库的读权限 |
| readWriteAnyDatabase  | 只在admin数据库中可用，赋予用户所有数据库的读写权限 |
| userAdminAnyDatabase  | 只在admin数据库中可用，赋予用户所有数据库的userAdmin权限 |
| dbAdminAnyDatabase  | 只在admin数据库中可用，赋予用户所有数据库的dbAdmin权限 |
| root  | 只在admin数据库中可用。超级账号，超级权限 |

1. 进入admin数据库
```sql
use admin
```

2. 创建管理员账户

```sql
db.createUser({ user: "admin", pwd: "pwd", roles: [{ role: "userAdminAnyDatabase", db: "admin" }] })
```

3. 创建root用户

```sql
db.createUser({user: "root",pwd: "pwd", roles: [ { role: "root", db: "admin" } ]})
```

4. 创建用户自己数据库的管理员用户

> 注：这时候一定，一定，一定要切换到所在数据库上去创建用户，不然创建的用户还是属于admin。

> 如果是读写角色的话，权限设置为role: "readWrite"

```sql
# 切换数据库
use db1

# 创建用户
db.createUser({user: "user",pwd: "pwd",roles: [ { role: "dbOwner", db: "db1" } ]})
```

5. 查看用户

```sql
show users
```

6. 删除用户

> 删除用户必须由账号管理员来删，所以，切换到admin角色

```sql
# 0. 切换管理员用户
db.auth("admin","pwd")

# 1. 删除单个用户
db.system.users.remove({user:"XXXXXX"})

# 2. 删除所有用户
db.system.users.remove({})
```

### 开启验证

1. 修改 mongod.cfg 

```conf
# 1. 首先，将bind_ip改为0.0.0.0 ，binIP关乎到访问连接的限制。

#bindIp: 0.0.0.0         #改成0，那么大家都可以访问
#bindIp: 127.0.0.1       #改成127，那就只能自己练了

# 2. 然后找到 #security：去掉#号，改成下面这样，开启安全认证。

security：
    authorization: enabled #注意缩进，参照其他的值来改，若是缩进不对可能导致后面服务不能重启
```

2. 重启MongoDB服务