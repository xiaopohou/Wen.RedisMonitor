# Wen.RedisMonitor
Redis 简单的监控平台，基于 MVC

![image](https://github.com/liqingwen2015/Wen.RedisMonitor/blob/master/images/1.jpg)

![image](https://github.com/liqingwen2015/Wen.RedisMonitor/blob/master/images/2.jpg)

![image](https://github.com/liqingwen2015/Wen.RedisMonitor/blob/master/images/3.jpg)

![image](https://github.com/liqingwen2015/Wen.RedisMonitor/blob/master/images/4.jpg)

# Redis Info 命令
## http://www.runoob.com/redis/server-info.html 引用

Redis Info 命令以一种易于理解和阅读的格式，返回关于 Redis 服务器的各种信息和统计数值。
通过给定可选的参数 section ，可以让命令只返回某一部分的信息：
server : 一般 Redis 服务器信息，包含以下域：
redis_version : Redis 服务器版本
redis_git_sha1 : Git SHA1
redis_git_dirty : Git dirty flag
os : Redis 服务器的宿主操作系统
arch_bits : 架构（32 或 64 位）
multiplexing_api : Redis 所使用的事件处理机制
gcc_version : 编译 Redis 时所使用的 GCC 版本
process_id : 服务器进程的 PID
run_id : Redis 服务器的随机标识符（用于 Sentinel 和集群）
tcp_port : TCP/IP 监听端口
uptime_in_seconds : 自 Redis 服务器启动以来，经过的秒数
uptime_in_days : 自 Redis 服务器启动以来，经过的天数
lru_clock : 以分钟为单位进行自增的时钟，用于 LRU 管理
clients : 已连接客户端信息，包含以下域：
connected_clients : 已连接客户端的数量（不包括通过从属服务器连接的客户端）
client_longest_output_list : 当前连接的客户端当中，最长的输出列表
client_longest_input_buf : 当前连接的客户端当中，最大输入缓存
blocked_clients : 正在等待阻塞命令（BLPOP、BRPOP、BRPOPLPUSH）的客户端的数量
memory : 内存信息，包含以下域：
used_memory : 由 Redis 分配器分配的内存总量，以字节（byte）为单位
used_memory_human : 以人类可读的格式返回 Redis 分配的内存总量
used_memory_rss : 从操作系统的角度，返回 Redis 已分配的内存总量（俗称常驻集大小）。这个值和 top 、 ps 等命令的输出一致。
used_memory_peak : Redis 的内存消耗峰值（以字节为单位）
used_memory_peak_human : 以人类可读的格式返回 Redis 的内存消耗峰值
used_memory_lua : Lua 引擎所使用的内存大小（以字节为单位）
mem_fragmentation_ratio : used_memory_rss 和 used_memory 之间的比率
mem_allocator : 在编译时指定的， Redis 所使用的内存分配器。可以是 libc 、 jemalloc 或者 tcmalloc 。
在理想情况下， used_memory_rss 的值应该只比 used_memory 稍微高一点儿。
当 rss > used ，且两者的值相差较大时，表示存在（内部或外部的）内存碎片。
内存碎片的比率可以通过 mem_fragmentation_ratio 的值看出。
当 used > rss 时，表示 Redis 的部分内存被操作系统换出到交换空间了，在这种情况下，操作可能会产生明显的延迟。
当 Redis 释放内存时，分配器可能会，也可能不会，将内存返还给操作系统。
如果 Redis 释放了内存，却没有将内存返还给操作系统，那么 used_memory 的值可能和操作系统显示的 Redis 内存占用并不一致。
查看 used_memory_peak 的值可以验证这种情况是否发生。
persistence : RDB 和 AOF 的相关信息
stats : 一般统计信息
replication : 主/从复制信息
cpu : CPU 计算量统计信息
commandstats : Redis 命令统计信息
cluster : Redis 集群信息
keyspace : 数据库相关的统计信息
