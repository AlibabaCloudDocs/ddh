# RenewDedicatedHosts

调用RenewDedicatedHosts续费一台或者多台包年包月专有宿主机。

## 接口说明

续费付款时，优先使用可抵扣的代金券，且您的账号必须支持账号余额支付或信用支付。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=RenewDedicatedHosts&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|RenewDedicatedHosts|系统规定参数。取值：RenewDedicatedHosts |
|DedicatedHostIds|String|是|dh-bp199lyny9b3\*\*\*\*|专有宿主机的编号列表。最多可以输入100个预付费专有宿主机ID。多个专有宿主机ID用一个格式类似`["dh-xxxxxxxxx", "dh-yyyyyyyyy", … "dh-zzzzzzzzz"]`的JSON数组表示，ID之间用半角逗号（,）隔开。 |
|Period|Integer|是|1|续费周期。取值范围：请参见`PeriodUnit`参数的描述部分。 |
|RegionId|String|是|cn-hangzhou|专有宿主机所属的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|PeriodUnit|String|否|Month|续费时长单位。取值范围：

 -   Week：周。此时参数`Period`的取值范围：\{1, 2, 3, 4\}
-   Month（默认）：月。此时参数`Period`的取值范围：\{1, 2, 3, 4, 5, 6, 7, 8, 9, 12, 24, 36, 48, 60\} |
|ClientToken|String|否|123e4567-e89b-12d3-a456-426655440000|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。只支持ASCII字符，且不能超过64个字符。更多详情，请参见[如何保证幂等性](~~25693~~)。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|2A4EA075-CB5B-41B7-B0EB-70D339F64DE7|请求ID。 |

## 示例

请求示例

```
http(s)://ecs.aliyuncs.com/?Action=RenewDedicatedHosts
&DedicatedHostIds=dh-bp199lyny9b3****
&Period=1
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<RenewDedicatedHostsResponse>
    <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</RenewDedicatedHostsResponse>
```

`JSON` 格式

```
{
    "RequestId":"2A4EA075-CB5B-41B7-B0EB-70D339F64DE7"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|IdempotenceParamNotMatch|Request uses a client token in a previous request but is not identical to that request.|与相同ClientToken的请求参数不符合。|
|400|InvalidClientToken.ValueNotSupported|The ClientToken provided is invalid.|指定的ClientToken不合法。|
|403|ChargeTypeViolation|Pay-As-You-Go dedicated host do not support this operation.|按量付费的宿主机不支持当前操作。|
|403|IncorrectHostStatus|The current status of the resource does not support this operation.|当前资源的状态不支持此操作。|
|400|InvalidPeriod|The specified period is not valid.|指定的时段不合法。|
|403|LastTokenProcessing|The last token request is processing.|正在处理上一条令牌请求，请您稍后再试。|
|400|InvalidPeriodUnit.ValueNotSupported|The specified parameter PeriodUnit is not valid.|参数PeriodUnit无效。|
|400|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|指定的专有宿主机不存在。|
|400|InvalidStatus.Upgrading|The dedicated host is upgrading, please try it later.|指定的专有宿主机正在升级，请稍后操作。|
|500|InternalError|The request processing has failed due to some unknown error.|内部错误，请重试。如果多次尝试失败，请提交工单。|
|400|LastOrderProcessing|The previous order is still processing, please try again later.|订单正在处理中，稍后重试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Ecs)查看更多错误码。

