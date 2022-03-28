<!--
 * @Description: 
 * @Author: LLiuHuan
 * @Date: 2022-03-25 19:09:46
 * @LastEditTime: 2022-03-28 09:14:23
 * @LastEditors: LLiuHuan
-->

### 基础
> 文档：[https://redis.io/commands/](https://redis.io/commands/)

```bash
redis-server /path/redis.conf        # 使用相关配置文件启动redis  
redis-cli                            # 打开redis客户端  
sudo systemctl restart redis.service # 重启redis服务  
sudo systemctl status redis          # 查看redis状态  
```

### 字符串[STRING]

```bash
APPEND key value                  # 如果 key 已经存在并且是一个字符串， APPEND 命令将指定的 value 追加到该 key 原来值（value）的末尾。
BITCOUNT key [start end]          # 返回字符串的字节数。
SET key value                     # 设置指定 key 的值。
SETNX key value                   # 只有在 key 不存在时设置 key 的值。
SETRANGE key offset value         # 用 value 参数覆写给定 key 所储存的字符串值，从偏移量 offset 开始。
STRLEN key                        # 返回 key 所储存的字符串值的长度。
MSET key value [key value ...]    # 同时设置一个或多个 key-value 对。
MSETNX key value [key value ...]  # 同时设置一个或多个 key-value 对，当且仅当所有给定 key 都不存在。
GET key                           # 获取指定 key 的值。
GETRANGE key start end            # 返回 key 中字符串值的子字符。
MGET key [key ...]                # 获取所有(一个或多个)给定 key 的值。
INCR key                          # 将 key 中储存的数字值增一。
INCRBY key increment              # 将 key 所储存的值加上给定的增量值（increment）。
INCRBYFLOAT key increment         # 将 key 所储存的值加上给定的浮点增量值（increment）。
DECR key                          # 将 key 中储存的数字值减一。
DECRBY key decrement              # key 所储存的值减去给定的减量值（decrement）。
DEL key                           # 删除 key。

EXPIRE key 120                    # key 将在120秒内被删除。
TTL key                           # 返回 key 删除前的秒数。
```

### 列表[LIST]
> list 是一个有序的集合

```bash
RPUSH key value [value ...]           # 将新值放在列表的末尾(一个或多个)。
RPUSHX key value                      # 仅当值存在时，才在列表末尾追加值。
LPUSH key value [value ...]           # 将新值放在列表的开头(一个或多个)。
LPUSHX key value                      # 仅当值存在时，才在列表开头追加值。
LRANGE key start stop                 # 获取列表指定范围内的元素。
LINDEX key index                      # 通过索引获取列表中的元素。
LINSERT key BEFORE|AFTER pivot value  # 在列表的元素前或者后插入元素。
LLEN key                              # 获取列表长度。
LPOP key                              # 移出并获取列表的第一个元素。
LSET key index value                  # 通过索引设置列表元素的值。
LREM key number_of_occurrences value  # 移除列表元素。
LTRIM key start stop                  # 对一个列表进行修剪(trim)，就是说，让列表只保留指定区间内的元素，不在指定区间之内的元素都将被删除。
RPOP key                              # 移除列表的最后一个元素，返回值为移除的元素。
RPOPLPUSH source destination          # 移除列表的最后一个元素，并将该元素添加到另一个列表并返回
BLPOP key [key ...] timeout           # 移出并获取列表的第一个元素， 如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为止。
BRPOP key [key ...] timeout           # 移出并获取列表的最后一个元素， 如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为止。
```


### 集合[SET]
> 集合类似于列表，只是它没有特定的顺序。  
> 每个元素只能出现一次。

```bash
SADD key member [member ...]     # 将给定值添加到集合中(一个或多个)
SCARD key                        # 获取集合中的成员数。
SREM key member [member ...]     # 从集合中删除给定的值(一个或多个)。
SISMEMBER myset value            # 测试给定值是否在集合中。
SMEMBERS myset                   # 返回此集合中所有成员的列表。
SUNION key [key ...]             # 组合两个或多个集合并返回所有元素的列表。
SINTER key [key ...]             # 返回给定所有集合的交集。
SMOVE source destination member  # 将成员从一个集合移动到另一个集合(将 member 元素从 source 集合移动到 destination 集合)。
SPOP key [count]                 # 移除并返回集合中的一个随机成员。
```

### 有序集合[SORTED SETS]
> 排序集类似于常规集，但现在每个值都有一个关联的分数。  
> 该分数用于对集合中的元素进行排序。

```bash
ZADD key [NX|XX] [CH] [INCR] score member [score member ...]  # 向有序集合添加一个或多个成员，或者更新已存在成员的分数。

ZCARD key                           # 获取有序集合的成员数。
ZCOUNT key min max                  # 计算在有序集合中指定区间分数的成员数。
ZINCRBY key increment member        # 有序集合中对指定成员的分数加上增量 increment 。
ZRANGE key start stop [WITHSCORES]  # 通过索引区间返回有序集合指定区间内的成员。
ZRANK key member                    # 返回有序集合中指定成员的索引。
ZREM key member [member ...]        # 移除有序集合中的一个或多个成员。
ZREMRANGEBYRANK key start stop      # 移除有序集合中给定的排名区间的所有成员。
ZREMRANGEBYSCORE key min max        # 移除有序集合中给定的分数区间的所有成员。
ZSCORE key member                   # 返回有序集中，成员的分数值

ZRANGEBYSCORE key min max [WITHSCORES] [LIMIT offset count]  # 返回有序集中指定分数区间内的成员，分数从高到低排序
```

### 哈希[HASHES]
> 哈希是字符串字段和字符串值之间的映射，  
> 因此，它们是表示对象的完美数据类型。

```bash
HGET key field          # 获取存储在哈希表中指定字段的值。
HGETALL key             # 获取在哈希表中指定 key 的所有字段和值。
HSET key field value    # 将哈希表 key 中的字段 field 的值设为 value。
HSETNX key field value  # 只有在字段 field 不存在时，设置哈希表字段的值。

HMSET key field value [field value ...]  # 同时将多个 field-value (域-值)对设置到哈希表 key 中。

HINCRBY key field increment  # 为哈希表 key 中的指定字段的整数值加上增量 increment 。
HDEL key field [field ...]   # 删除一个或多个哈希表字段。
HEXISTS key field            # 查看哈希表 key 中，指定的字段是否存在。
HKEYS key                    # 获取所有哈希表中的字段。
HLEN key                     # 获取哈希表中字段的数量。
HSTRLEN key field            # 获取哈希表的长度。
HVALS key                    # 获取哈希表中所有值。
```


### HYPERLOGLOG
> HyperLogLog使用随机化来提供数字的近似值  
> 在一个集合中使用一个恒定的、少量的内存
> 2.8.9 版本添加的，是用来做基数统计的算法，HyperLogLog 的优点是，在输入元素的数量或者体积非常非常大时，计算基数所需的空间总是固定 的、并且是很小的。  

```bash
PFADD key element [element ...]  # 添加指定元素到 HyperLogLog 中。
PFCOUNT key [key ...]            # 返回给定 HyperLogLog 的基数估算值。

PFMERGE destkey sourcekey [sourcekey ...]  # 将多个 HyperLogLog 合并为一个 HyperLogLog
```

### 发布订阅[PUBLICATION & SUBSCRIPTION]

```bash
PSUBSCRIBE pattern [pattern ...]             # 订阅一个或多个符合给定模式的频道。
PUBSUB subcommand [argument [argument ...]]  # 查看订阅与发布系统状态。
PUBLISH channel message                      # 将信息发送到指定的频道。
PUNSUBSCRIBE [pattern [pattern ...]]         # 退订所有给定模式的频道。
SUBSCRIBE channel [channel ...]              # 订阅给定的一个或多个频道的信息。
UNSUBSCRIBE [channel [channel ...]]          # 指退订给定的频道。
```

### 其他命令[OTHER COMMANDS]

```bash
KEYS pattern  # 查找所有符合给定模式( pattern)的 key 。
```