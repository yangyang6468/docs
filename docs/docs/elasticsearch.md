**一、基本概念**

索引：含有相同属性的文档的集合。　　　　　　　　　　　　　　　//可以想象成一个数据库 database

类型：索引可以定义一个或多个类型，文档必须属于一个类型。　　　//可以想象成数据库中的表 table

文档：文档是可以被索引的基本数据单位。　　　　　　　　　　　　//可以想象成数据库表中的一条数据

分片：每一个索引有多个分片，每个分片都是一个Lucene索引

备份：拷贝一份备份就完成了分片的备份

每创建一个所以默认会创建5个分片和一个备份，当主分片出问题时，备份可以代替工作；备份的分片还可以执行搜索操作