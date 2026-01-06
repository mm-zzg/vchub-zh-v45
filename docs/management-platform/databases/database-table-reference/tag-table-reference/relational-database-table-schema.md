# 关系型数据库表结构说明

SQLite、SQLServer、PostgreSQL、MySQL这4种传统关系型数据库共享同一套表结构定义   

## 边历史库

变量历史库在数据库中至少使用3种不同的表

| **表名称**| **表说明**| **列引用**|
|:---------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ScadaProviderMapping                                                | 历史数据来源节点和历史库名称的注册表，用于标识历史数据来源| ScadaTagMapping.ProviderId = ScadaProviderMapping.Id  ScadaTagHistory.ProviderId = ScadaProviderMapping.Id  ScadaTagHistory_X_X_X.ProviderId = ScadaProviderMapping.Id |
| ScadaTagMapping                                                     | 历史数据变量和变量值类型注册表，用于注册变量和提供变量Id  | ScadaTagHistory.TagId = ScadaTagMapping.Id  ScadaTagHistory_X_X_X.TagId = ScadaTagMapping.Id  |
| ScadaTagHistory                                                     | 此表存储原始变量历史数据，当历史库配置选择不分区时，数据存储到此表 |  
| ScadaTagHistory_{**ProvideId**}_{**PartitonSize**}_{**DateKey**}    | 此表存储原始变量历史数据，当历史库配置选择分区时，数据存储到此表  将有多个表适合此格式，具体取决于  <br>**ProviderId** **历史数据来源**(ScadaProviderMapping.Id)  <br>**PartitonSize 历史库分区大小**(day、week、month、quarter、halfyear、year)  <br>**DateKey 时间分区键**(根据当前时间和分区大小计算出的分区键)| 
| ScadaTagPreProcessed_{**ProvideId**}_{**WindowSize**}_{**DateKey**} | 此表存储着预处理数据，当历史库配置开启预处理时，会将原始数据按照预处理配置存储到此表中   将有多个表适合此格式，具体取决于  <br>**ProviderId** **历史数据来源**(ScadaProviderMapping.Id)  <br>**WindowSize 预处理时间窗口(历史库配置)**  <br>**DateKey 时间分区键**(根据原始数据时间按照yyyyMM分组)  | 

![alt text](2.png)



## ScadaProviderMapping

变量会绑定资产，资产会绑定历史库，历史库名称和当前历史数据来源的节点的节点名称构成了此表

历史数据来源节点的节点名称和历史库名称的注册表，用于标识历史数据来源。

| **列名称**   | **数据类型** | **描述**|
|:----------|:----------|:-------------------------------------------------------------------------------------|
| Id       | BigInt   | 自增 Id。<br>被表`ScadaTagMapping`、`ScadaTagHistory`、`ScadaTagHistory_X_X_X`所引用 |
| Node     | String   | 数据来源节点的节点名称                                                              |
| Provider | String   | 资产绑定的历史库的历史库名称或报警历史库名称                                        |



## ScadaTagMapping

历史数据变量和变量值类型注册表，用于注册变量和提供变量Id

| 列名称         | 数据类型 | 描述|
|:----------------|:----------|:---------------------------------------------------------------------------|
| Id             | BigInt   | 自增 Id。<br>被表`ScadaTagHistory`、`ScadaTagHistory_X_X_X`所引用           |
| Tag            | String   | 变量名称                                                                  |
| Type           | TinyInt  | 变量存储的数据类型  1: Integer 2: String 3: Double 4: Boolean 5: DateTime |
| ProviderId     | BigInt   | 来源 ScadaProviderMapping 的 Id                                           |
| NormalizedName | String   | 变量转中文拼音后的字符串                                                  |

## ScadaTagHistory Or ScadaTagHistory_{ProvideId}_ {PartitonSize}_{DateKey}

**存储原始变量历史数据**

当历史库配置关闭分区时，数据存储到 **ScadaTagHistory**

启用分区后，数据将按照以下命名约定存储在动态生成的表中：

**ScadaTagHistory_{ProvideId}_ {PartitonSize}_{DateKey}**

| 列名称      | 数据类型 | 描述                                                   |
|:-------------|:----------|:--------------------------------------------------------|
| TagId       | BigInt   | 来源 ScadaTagMapping 的 Id                             |
| ProviderId  | BigInt   | 来源 ScadaProviderMapping 的 Id                        |
| Quality     | Int      | 质量位                                                 |
| IntegerVal  | BigInt   | 如果变量的数据类型是Integer，则保存变量的值，否则为Null  |
| DoubleVal   | Double   | 如果变量的数据类型是Double，则保存变量的值，否则为Null   |
| BoolVal     | Boolean  | 如果变量的数据类型是Boolean，则保存变量的值，否则为Null  |
| StringVal   | String   | 如果变量的数据类型是String，则保存变量的值，否则为Null   |
| DateTimeVal | DateTime | 如果变量的数据类型是DateTime，则保存变量的值，否则为Null |
| Timestamp   | BigInt   | 变量值记录时的时间戳(毫秒)                             |

## ScadaTagPreProcessed_{ProvideId}_ {WindowSize}_{DateKey}

当历史库开启预处理时，会对原始数据表**ScadaTagHistory** Or **ScadaTagHistory_{ProvideId}_ {PartitonSize}_{DateKey}** 的原始数据进行预处理

根据预处理配置的时间窗口和时间，以及历史数据来源，创建对应的预处理表:
**ScadaTagPreProcessed_{provideId}_ {WindowSize}_{DateKey}**   

| 列名称           | 数据类型 | 描述 |
|:------------------|:----------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TagId            | BigInt   | 来源 ScadaTagMapping 的 Id |
| Category         | Int      | **采样类型** <br>1: Min <br>2: Max <br>3: Avg <br>- **IntegerVal** 列存储数据点的 **数量**，代表某一指定时间窗口或采样周期内的有效记录总数。<br>- **DoubleVal** 列存储根据上述数据点计算得出的 **平均值**（`Avg`）。 <br>4: Last <br>5: First <br>7: Count <br>11: CountOn And CountOff <br>- **IntegerVal** 列存储 **CountOn** 值，表示在定义的时间窗口内标签或信号切换到“开启”状态的次数。<br>- **DoubleVal** 列存储 **CountOff** 值，表示在同一时间段内切换到“关闭”状态的次数。  <br>12: DurationOn And DurationOff <br>- **IntegerVal** 列存储 DurationOn 值，表示标签或信号在指定时间窗口内保持“开启”状态的总时间（以秒为单位）。<br>- **DoubleVal** 列存储 DurationOff 值，表示标签在同一时间段内保持“关闭”状态的总时间（以秒为单位）。|
| Timestamp        | BigInt   |当预处理时间窗口设置为 **2 分钟** 时，系统将通过以下公式计算每个标签值对应的时间戳： <br>`Timestamp = floor(TagTime / (2 × 60 × 2000)) × (2 × 60 × 2000)`  <br>该公式的作用是，将标签的原始时间对齐至其所属 2 分钟时间窗口的起始时刻。例如,若某标签值的时间落在 `2028-08-01 01:00:00  ~ 2028-08-01 01:02:00` 这个时间范围内，系统会为该预处理记录分配统一的时间戳 `2028-08-01 01:00:00`。|
| Quality          | Int      | 质量位 |
| IntegerVal       | BigInt   | - 如果变量的数据类型是 `1` (Integer)，则保存变量的值，否则为 `Null` <br>- 当采样类型为`Avg`时，此列存储的时这个采样区间该变量 **原始数据的数量**  <br>- 当采样类型为`Count`时，此列存储的时这个采样区间该变量 **原始数据的数量**  <br>- 当采样类型为`CountOn And CountOff`时，此列存储的是 **CountOn** 的值,表示标签进入“开启”状态的次数。  <br>- 当采样类型为`DurationOn And DurationOf`时，此列存储的是**DurationOn** 的值,表示标签处于“开启”状态的总时间。 |
| DoubleVal        | Double   | - 如果变量的数据类型是 `3` (Double)，则保存变量的值，否则为`Null`  <br>- 当采样类型为 `Avg` 时，此列存储的时这个采样区间该变量原始数据的 **平均值**  <br>- 当采样类型为`CountOn And CountOff`时，此列存储的是**CountOff** 的值,表示标签进入“关闭”状态的次数。  <br>- 当采样类型为`DurationOn And DurationOff`时，此列存储的是 **DurationOff** 的值,表示标签处于“关闭”状态的总时间。|
| BoolVal          | Boolean  | 如果变量的数据类型是`4` (Boolean)，则保存变量的值，否则为`Null` |
| StringVal        | String   | 如果变量的数据类型是`2` (String)，则保存变量的值，否则为`Null`   |
| DateTimeVal      | DateTime | 如果变量的数据类型是`5` (DateTime)，则保存变量的值，否则为`Null` |
| CollectTimestamp | BigInt   | 记录时间反映的是与当前采样类型下数据源对应的时间戳。若数据源未提供明确的记录时间，系统将默认采用与时间戳（Timestamp）字段相同的值。 |



## 说明

#### ProviderId

`ScadaProviderMapping` 表的主键 ID 用于对每个 SCADA 数据提供方配置进行唯一标识。在 `ScadaTagHistory`、`ScadaTagMapping` 等关联表中，该 ID 以 `ProviderId` 字段的形式存在，作为外键用于建立标签记录与其对应数据提供方之间的关联完整性。

#### WindowSize

预处理时间窗口的配置值，决定了数据预处理过程中所采用的 **采样间隔**。该配置值定义了原始历史数据将如何按时间维度进行分组与聚合。例如，若将时间窗口设为 **2 分钟**，系统会对每个 2 分钟时间间隔内的所有标签值进行聚合处理，且每个时间窗口对应生成一条预处理记录。

#### Datekey

根据历史数据的原始数据的时间，结合分区类型计算出的分区Key

| **分区类型** | **计算逻辑** |
|:----------|:-------------------------------------------------------------------------------------------------------------------|
| day      | 历史数据变量值记录 UTC 时间 按 `yyyyMMdd` 格式化 **例: 20241105**                                                       |
| week     |  UTC **星期一** 作为每周起始。从每年的 **1 月 1 日** 开始计算周排序(排序索引从 1 开始) **例: 202445** |
| month    | UTC 时间格式为 `yyyyMM`。例如：202411 |
| quarter  | UTC 时间格式为 `yyyyQ`，其中 `Q` 的取值范围为 `1` 到 `4`。例如：**20244** |
| halfyear | UTC 时间格式为 `yyyyH`，其中 `H` 为 `1` 表示上半年，为 `2` 表示下半年。例如：**20242** |
| year     | UTC 时间格式为 `yyyy`。例如：**2024**|

