# ModifyDedicatedHostsChargeType

调用ModifyDedicatedHostsChargeType修改专有宿主机的付费类型。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostsChargeType&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDedicatedHostsChargeType|系统规定参数。取值：ModifyDedicatedHostsChargeType |
|DedicatedHostIds|String|是|\["dh-bp181e5064b5sotr\*\*\*\*","dh-bp18064b5sotrr9c\*\*\*\*"\]|专有宿主机ID。取值可以由多台专有宿主机ID组成一个JSON数组，最多支持20个ID，ID之间用半角逗号（,）隔开。 |
|RegionId|String|是|cn-hangzhou|专有宿主机所属的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|Period|Integer|否|1|包年包月续费时长。取值范围：

 -   `PeriodUnit=Week`时，`Period`的有效取值：\{1, 2 ,3 ,4\}
-   `PeriodUnit=Month`时，`Period`的有效取值：\{1, 2, 3, 4, 5, 6, 7, 8, 9, 12, 24, 36, 48, 60\} |
|PeriodUnit|String|否|Month|续费时长的时间单位，即参数`Period`的单位。取值范围：

 -   Week
-   Month

 默认值：Month |
|DryRun|Boolean|否|false|是否只预检此次请求。取值范围：

 -   true：发送检查请求，不会查询资源状况。检查项包括AccessKey是否有效、RAM用户的授权情况和是否填写了必需参数。如果检查不通过，则返回对应错误。如果检查通过，会返回错误码`DryRunOperation`。
-   false：发送正常请求，通过检查后返回2XX HTTP状态码并直接查询资源状况。

 默认值：false |
|AutoPay|Boolean|否|false|是否自动支付。取值范围：

 -   true：自动支付。您需要确保账户余额充足，如果账户余额不足会生成异常订单，并只能作废订单。
-   false：只生成订单不扣费。

 默认值：true

 **说明：** 如果您的支付方式余额不足，可以将参数`AutoPay`置为`false`，此时会生成未支付订单，您可以自行支付。 |
|DedicatedHostChargeType|String|否|PrePaid|专有宿主机需要修改的目标计费方式。取值范围：

 -   PrePaid：将按量付费转换为包年包月。
-   PostPaid：将包年包月转换为按量付费。

 默认值：PrePaid |
|ClientToken|String|否|e4567-e89b-12d3-a456-426655440000|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。`ClientToken`只支持ASCII字符，且不能超过64个字符。更多详情，请参见[如何保证幂等性](~~25693~~)。 |
|DetailFee|Boolean|否|false|包年包月转换为按量付费时，是否返回订单费用详情。

 默认值：false |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|FeeOfInstances|Array of FeeOfInstance| |订单费用详情。 |
|FeeOfInstance| | | |
|Currency|String|CNY|账单费用货币单位。 |
|Fee|String|0|费用数值。 |
|InstanceId|String|dh-bp181e5064b5sotrr\*\*\*\*|专有宿主机ID。 |
|OrderId|String|20413515388\*\*\*\*|生成的订单ID。 |
|RequestId|String|B61C08E5-403A-46A2-96C1-F7B1216DB10C|请求ID。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostsChargeType
&RegionId=cn-hangzhou
&InstanceIds=["dh-bp181e5064b5sotr****","dh-bpe5064b5sotrr9c****"]
&Period=1
&PeriodUnit=Month
&AutoPay=false
&IncludeAllDisks=true
&ClientToken=e4567-e89b-12d3-a456-426655440000
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyDedicatedHostsChargeTypeResponse>
      <RequestId>B61C08E5-403A-46A2-96C1-F7B1216DB10C</RequestId>
      <OrderId>20413515388****</OrderId>
      <FeeOfInstances>
            <FeeOfInstance>
                  <Fee>0</Fee>
                  <InstanceId>dh-bp181e5064b5sotr****</InstanceId>
                  <Currency>CNY</Currency>
            </FeeOfInstance>
            <FeeOfInstance>
                  <Fee>0</Fee>
                  <InstanceId>dh-bp181e5064b5sotr****</InstanceId>
                  <Currency>CNY</Currency>
            </FeeOfInstance>
      </FeeOfInstances>
</ModifyDedicatedHostsChargeTypeResponse>
```

`JSON` 格式

```
{
    "RequestId":"B61C08E5-403A-46A2-96C1-F7B1216DB10C",
    "OrderId":"20413515388****",
    "FeeOfInstances":
    {
        "FeeOfInstance":[
            {
                "Fee":"0",
                "InstanceId":"dh-bp181e5064b5sotr****",
                "Currency":"CNY"
            },
            {
                "Fee":"0",
                "InstanceId":"dh-bp181e5064b5sotr****",
                "Currency":"CNY"
            }
        ]
    }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidParameter.InstanceIds|The specified InstanceIds are invalid.|指定的实例无效。|
|400|InvalidParameter|%s|无效的参数。|
|400|InvalidStatus.ValueNotSupported|%s|该资源当前的状态不支持此操作。|
|400|InvalidInstanceChargeType.ValueNotSupported|%s|暂不支持此付款类型，请核对相关信息后重试。|
|400|ExpiredInstance|The specified instance has expired.|指定的实例已过期。|
|400|InstancesIdQuotaExceed|The maximum number of Instances is exceeded.|超过了实例数的上限。|
|400|InvalidClientToken.ValueNotSupported|The ClientToken provided is invalid.|指定的ClientToken不合法。|
|403|InvalidInstanceType.ValueNotSupported|The specified InstanceType does not exist or beyond the permitted range.|您指定的实例规格不存在，或者您没有权限操作此规格的实例。|
|403|InstanceType.Offline|%s|实例规格已停售或者供货不足。|
|500|InternalError|The request processing has failed due to some unknown error, exception or failure.|内部错误，请重试。如果多次尝试失败，请提交工单。|
|400|ReleaseTimeHaveBeenSet|The specified instance has been set released time.|指定的实例已设置释放时间。|
|403|InvalidAccountStatus.NotEnoughBalance|Your account does not have enough balance.|账号余额不足，请您先充值再进行该操作。|
|403|Account.Arrearage|Your account has an outstanding payment.|您的账号存在未支付的款项。|
|400|Throttling|Request was denied due to request throttling, please try again after 5 minutes.|您当前的请求被流控，请5分钟后重试。|
|403|InvalidParameter.NotMatch|%s|您输入的参数无效，请检查参数之间是否冲突。|
|403|InvalidAction|%s|操作无效。|
|400|Throttling|%s|请求被流控。|
|400|QuotaExceed.AfterpayInstance|The maximum number of Pay-As-You-Go instances is exceeded: %s|按量付费的实例库存不足，请减少创建数量。|
|400|InvalidPeriod.UnitMismatch|The specified Period must be correlated with the PeriodUnit.|指定的时长必须与PeriodUnit关联。|
|400|InvalidImageType.NotSupported|%s|指定的镜像类型无效，请查询本地域是否支持此镜像类型。|
|400|InvalidPeriod.ExceededDedicatedHost|Instance expired date can't exceed dedicated host expired date.|实例过期日期不能超过专有宿主机的过期日期。|
|403|QuotaExceed.PostPaidDisk|Living postPaid disks quota exceeded.|按量付费磁盘数量已超出允许数量。|
|403|ImageNotSupportInstanceType|The specified instanceType is not supported by instance with marketplace image.|指定的市场镜像不支持该实例规格。|
|403|InvalidInstanceType.PhasedOut|This instanceType is no longer offered.|您指定的实例规格已下线不再出售。|
|400|InvalidSystemDiskCategory.ValueNotSupported|%s|当前操作不支持此系统磁盘类型。|
|500|InternalError|The request processing has failed due to some unknown error.|内部错误，请重试。如果多次尝试失败，请提交工单。|
|403|RealNameAuthenticationError|Your account has not passed the real-name authentication yet.|您的帐户尚未通过实名认证，请先实名认证后再操作。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Ecs)查看更多错误码。

