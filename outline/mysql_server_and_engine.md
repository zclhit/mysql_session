# Mysql服务端与引擎

客户端 -> Server层 -> 存储引擎层

不同存储引擎共用一个server层

 

**连接器**

管理连接，基于tcp/ip，基于socket

 

**缓存管理**

缓存功能，mysql 8.0后被取消

 

**分析器**

词法分析 - 识别每个字符串和空格都是什么

语法分析 - 判断是否满足MySql要求的语法格式

 

**优化器**

决定使用哪个索引，决定多表关联过程中的关联关系

 

**执行器**

权限校验，控制与引擎交互完成查询工作

 

**日志模块**

redo log 和 bin log

Redo log: Write-Ahead Logging

先把操作写到日志里面，然后innodb引擎自己决定什么时候落到磁盘中

通过redo log，可以保证使用了innodb引擎的Mysql数据库是crash safe的

 

bin log 只用于归档，没有crash safe能力，不是innodb引擎特有的

 

redo log通过两阶段提交实现了crash safe