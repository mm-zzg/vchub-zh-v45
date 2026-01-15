# System.Alarm.queryHistory

## 描述

查询当前历史存储的历史报警。

## 语法

**System.Alarm.queryHistory(historyStorage:string): Promise`<any>`**
**System.Alarm.queryHistory(historyStorage:string,params:{**
**startTime?: Date | string,**
**endTime?: Date | string,**
**priority?: AssetAlarmPriority | AssetAlarmPriority[],**
**state?: AssetAlarmState | AssetAlarmState[],**
**path?: string | string[],**
**type?: AssetAlarmType | AssetAlarmType[],**
**asset?: string | string[],**
**expression?: string}): Promise`<any>`**
-参数
historyStorage - 历史存储名称
params  - 查询条件对象，可选参数
{
startTime? - 开始时间，默认为当前时间前8小时
endTime? - 结束时间，默认为当前时间
priority? -  单个或多个等级，可选值为“Low”，“Medium”，“High”，“Critical”
state? - 单个或多个状态，可选值为“Active”，“Unacked”，“Acked”，“Cleared”
path? - 单个或多个报警路径
type? - 单个或多个类型，可选值为"H"，"H2"，"H3"，"H4"，"L"，"L2"，"L3"，"L4"，"RateOfChange"，"Equivalent"，"TrueToFalse"，"FalseToTrue"
asset? - 单个或多个资产
expression? - 表达式，例1：priority == "Low"，例2：path.Contains("Device")，例3：state.HasFlag("Active") && stae.HasFlag("“Unacked")

}
-返回
[
{
path: string //报警路径
name: string //报警名称
type: string //类型
priority: string //等级
eventId: string //状态变更Id
eventTime: string //状态变更时间
state: string //状态
operator: string //确认人
valueType: string //值类型
value: string //报警值
ackTime: string  //确认时间
ackNotes: string //确认信息
ackMode: string //确认模式
nodeName: string //节点名称
storageName: string //历史存储名称
description: string //描述
},
...
]  

## 代码示例 

查询历史存储为"Default"最近8小时的历史报警。

```typescript 
const value = await System.Alarm.queryHistory("Default");
console.log(value);
```   
查询历史存储为"Default"，时间范围为“2025-03-10 00:00:00”至“2025-03-11 00:00:00”，报警等级为“High”，类型为“H”或“H2”，且状态为 "Active,Unacked"的历史报警。

```typescript
const value = await System.Alarm.queryHistory("Default",{startTime:'2025-03-10 00:00:00',endTime:'2025-03-11 00:00:00',priority:"High",type:["H","H2"],expression:'state.HasFlag("Active") && state.HasFlag("Unacked")'});
console.log(value);
``` 

