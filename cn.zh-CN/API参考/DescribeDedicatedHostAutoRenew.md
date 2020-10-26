# DescribeDedicatedHostAutoRenew

调用DescribeDedicatedHostAutoRenew查询一台或多台包年包月专有宿主机自动续费状态。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=DescribeDedicatedHostAutoRenew&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDedicatedHostAutoRenew|系统规定参数。取值：DescribeDedicatedHostAutoRenew |
|DedicatedHostIds|String|是|dh-bp165p6xk2tlw61e\*\*\*\*,dh-bp1f9vxmno\*\*\*\*|专有宿主机ID。最多可以输入100个包年包月专有宿主机ID，ID之间用半角逗号（,）隔开。 |
|RegionId|String|是|cn-hangzhou|专有宿主机所属的地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DedicatedHostRenewAttributes|Array of DedicatedHostRenewAttribute| |专有宿主机自动续费属性数组。 |
|DedicatedHostRenewAttribute| | | |
|AutoRenewEnabled|Boolean|true|是否自动续费。 |
|DedicatedHostId|String|dh-bp165p6xk2tlw61e\*\*\*\*|专有宿主机ID。 |
|Duration|Integer|0|自动续费时长。 |
|PeriodUnit|String|Month|续费单位。可能值：

 -   Week
-   Month |
|RenewalStatus|String|Normal|是否自动续费包年包月专有宿主机。取值范围：

 -   AutoRenewal：自动续费。
-   Normal：待续费。
-   NotRenewal：不续费，也不发送到期提醒。到期前第三天我们会发送不续费提醒。不续费的专有宿主机可以设置成待续费（Normal），再自行续费（[RenewDedicatedHosts](~~93287~~)）或设置为自动续费（AutoRenewal）。 |
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostAutoRenew
&RegionId=cn-hangzhou
&DedicatedHostIds=dh-bp165p6xk2tlw61e****,dh-bp1f9vxmno****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDedicatedHostAutoRenewResponse>
      <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
      <DedicatedHostRenewAttributes>
            <DedicatedHostRenewAttribute>
                  <DedicatedHostId>dh-bp165p6xk2tlw61e****</DedicatedHostId>
                  <Duration>0</Duration>
                  <AutoRenewEnalbed>false</AutoRenewEnalbed>
                  <PeriodUnit>Month</PeriodUnit>
                  <RenewalStatus>Normal</RenewalStatus>
            </DedicatedHostRenewAttribute>
             <DedicatedHostRenewAttribute>
                  <DedicatedHostId>dh-bp1f9vxmno****</DedicatedHostId>
                  <Duration>1</Duration>
                  <PeriodUnit>Month</PeriodUnit>
                  <AutoRenewEnalbed>true</AutoRenewEnalbed>
                  <RenewalStatus>AutoRenewal</RenewalStatus>
            </DedicatedHostRenewAttribute>
      </DedicatedHostRenewAttributes>
</DescribeDedicatedHostAutoRenewResponse>
```

`JSON` 格式

```
{
    "DedicatedHostIdRenewAttributes": {
        "DedicatedHostIdRenewAttribute": [
            {
                "Duration": 0,
                "DedicatedHostId": "dh-bp165p6xk2tlw61e****",
                "AutoRenewEnabled": false,
                "RenewalStatus": "Normal",
                "PeriodUnit": "Month"
            },
            {
                "Duration": 1,
                "DedicatedHostId": "dh-bp1f9vxmno****",
                "AutoRenewEnabled": true,
                "RenewalStatus": "AutoRenewal",
                "PeriodUnit": "Month"
            }
        ]
    },
    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|MissingParameter.DedicatedHostId|DedicatedHostId should not be null.|参数DedicatedHostId不能为空。|
|403|InvalidParameter.ToManyDedicatedHostIds|DedicatedHostId should be less than 100.|参数DedicatedHostIds包含的专有宿主机ID应该少于100个。|
|403|InvalidParameter.InvalidDedicatedHostId|%s|指定的参数DedicatedHostId无效。|
|403|IncorrectDedicatedHostStatus|The current status of the resource does not support this operation.|当前资源的状态不支持此操作。|
|403|ChargeTypeViolation|Pay-As-You-Go dedicated host do not support this operation.|按量付费的宿主机不支持当前操作。|

访问[错误中心](https://error-center.aliyun.com/status/product/Ecs)查看更多错误码。

