# InfluxDB表结构

**InfluxDB 表结构概述** 与传统的关系型数据库不同，InfluxDB 采用 **基于测量的模型**，而非基于表的模式。其数据结构针对时间序列数据进行了优化，包括带时间戳的指标和事件。主要区别包括：

- **测量集**：功能等同于表，但专为存储时序数据设计。
- **标签**：带索引的元数据，用于过滤与分组操作，类似关系型数据库中的索引列。
- **字段**：实际的业务数据值，不建立索引，此设计旨在优化写入性能
- **时间戳**：每条记录均自带时间戳，是 InfluxDB 数据模型的核心。

## Measurement结构说明

配置好 InfluxDB 数据库连接并在历史数据库中使用后，当历史数据启用标签时，数据将被写入 InfluxDB。VC Hub 系统会自动在内部创建相应的测量集。

## tag_{HistoryDatabaseName}_{NodeName}

变量历史库的Measurement名称以 `tag_` 开头，其中 `HistoryDatabaseName` 是该变量绑定的资产所配置历史库的历史库名称，`NodeName` 是该历史数据产生的节点的节点名称  

例如变量名称为 `HistoryAsset:Device.record`，这个变量所绑定的资产名称是`HistoryAsset`，查看`HistoryAsset`所配置的历史库，这个历史库名称假设为 `InfluxDbHisotry`，VC Hub系统的节点名称为`PC-SZ-JJG`，那么在InlfuxDb中Measurement的名称就是: **tag_InfluxDbHisotry_PC-SZ-JJG**

![alt text](1.png)



| 列名称 | 列类型 | 值类型  | 说明 |
|:--------|:--------|:---------|:--------------------------------------------------------------------------------------------------------------|
| P      | Tag    | string  | 变量名称 |
| T      | Tag    | string  | 值类型的数字字符串  1: Integer  2: String  3: Double  4: Boolean  5: DateTime                                |
| Q      | Field  | Integer | 质量位|
| IV     | Field  | Integer | 当T="1"时，该列存储对应值，否则为Null |
| DV     | Field  | float   | 当T="3"时，该列存储对应值，否则为Null   |
| BV     | Field  | boolean | 当T="4"时，该列存储对应值，否则为Null|
| BIV    | Field  | integer | 当T="4"时，该列存储对应值 true存1 false存0，否则为Null                                                         |
| DTV    | Field  | string  | 当T="5"时，该列存储对应值   会将时间转换为UTC时间后，按照 `yyyy-MM-ddTHH:mm:ss.fffZ` 格式化为字符串存入，否则为Null |
| SV     | Field  | string  | 当T="2"时，该列存储对应值，否则为Null |

