# 创建mongos实例 - CreateUDBRouteInstance

## 简介

创建mongos实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBRouteInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBRouteInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DBTypeId** | string | DB类型id，mongodb按版本细分有1：mongodb-2.4，2：mongodb-2.6,3：mongodb-3.0，4：mongodb-3.2 |**Yes**|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **Port** | int | 端口号，mongodb默认27017 |**Yes**|
| **ParamGroupId** | int | DB实例使用的配置参数组id |**Yes**|
| **MemoryLimit** | int | 内存限制(MB)，目前支持以下几档 600M/1500M/3000M /6000M/15000M/30000M |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 500G |**Yes**|
| **ConfigsvrId.N** | string | 配置服务器的dbid，允许一个或者三个。 |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Month |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **UseSSD** | boolean | 是否使用SSD，默认为ture |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | db实例id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDBRouteInstance
&Region=cn-bj2
&DBTypeId=mongodb-2.6
&ChargeType=Month   
&Name=udb-xxxxxxx
&Port=27017
&ParamGroupId=23
&MemoryLimit=600
&DiskSpace=20
&ConfigsvrId.0=udb-xxxxx
&ConfigsvrId.1=udb-xxxxx
&ConfigsvrId.2=udb-xxxxx
&ShardedClusterId=EmlJjnIa
```

### 响应示例
    
```json
{
  "Action": "CreateUDBRouteInstanceResponse",
  "DBId": "udb-xxxxx",
  "RetCode": 0
}
```





