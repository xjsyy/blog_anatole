---
title: "Common operation used by Redis"
date: 2023-11-03T02:55:16-05:00
categories: 
    - Database
    - redis
tags: ["redis"]
---
# 0.Overview

        基于内存的key-value 结构数据库，读写性能高，适合热点数据存储

# 1. 常用数据类型

- string:字符串

- 哈希:hash

- 列表:list

- 集合:set

- 有序集合:sorted set / zset

# 2. 字符串操作常用命令

1. SET key value:设定指定key的值

2. GET key: 获取指定key的值

3. SETEX key seconds value:设置指定key的值,并将key的过期时间设为seconds秒

4. SETNX key value:只有在key不存在时设置key的值

# 3. 哈希操作常用命令

1. HSET key field value:将哈希表 key 中的字段 field 的值设为 value

2. HGET key field: 获取存储在哈希表中指定字段的值

3. HDELE key field:删除存储在哈希表中的指定字段

4. HKETY key:获取哈希表中所有字段

5. HVALS key value:获取哈希表中所有值

# 4. 列表操作常用命令

1. LPUSH key value1 ....:将一个或多个值插入到列表头部

2. LRANGE key start stop:获取列表指定范围内的元素

3. RPOP:移除并获取列表最后一个元素

4. LLEN key:获取列表长度

# 5.集合操作常用命令

1. SADD key member1 ...:向集合添加一个或多个成员

2. SMEMBERS key: 返回集合中的所有成员

3. SCARD key:获取集合的成员数

4. SINTER key1 ...:返回给定所有集合的交集

5. SUNION key1 ....:返回所有给定集合的并集

6. SREM key member1 ...:删除集合中一个或多个成员

# 6. 有序集合操作常用命令

1. ZADD key score1 member1:向有序集合添加一个或多个成员

2. ZRANGE key start stop:通过索引区间返回有序集合中指定区间内的成员

3. ZINCRBY key increment member:有序集合中对指定成员的分数加上增量increment

4. ZREM key memeber:移除有序集合中的一个或多个成员

# 7. 通用操作命令

1. KEYS pattern:查找所有符合给定模式(pattern)的 key

2. EXISTS key:检查给定key是否存在

3. TYPE key:返回 key 所储存的值的类型

4. DEL key:该命令用于在key 存在是删除 key
