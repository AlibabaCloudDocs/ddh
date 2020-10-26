# ModifyDedicatedHostAutoReleaseTime

调用ModifyDedicatedHostAutoReleaseTime为一台按量付费专有宿主机设定自动释放时间，或者取消自动释放一台按量付费专有宿主机。

## 接口说明

到达设置的自动释放时间后，按量付费专有宿主机会被自动释放。请确保您已经不再使用该宿主机，并已按需备份应用数据。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostAutoReleaseTime&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDedicatedHostAutoReleaseTime|系统规定参数。取值：ModifyDedicatedHostAutoReleaseTime |
|DedicatedHostId|String|是|dh-bp165p6xk2tlw61e\*\*\*\*|需要自动释放的专有宿主机ID。 |
|RegionId|String|是|cn-hangzhou|专有宿主机所属的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|AutoReleaseTime|String|否|2019-06-04T13:35:00Z|专有宿主机的自动释放时间。按照ISO8601标准表示，并使用UTC+0时间，格式为yyyy-MM-ddTHH:mm:ssZ。

 -   必须晚于当前时间起算的半小时及以后。
-   必须早于当前时间起算的三年及以前。
-   如果参数值中的秒（ss）不是00，则自动取为00。
-   如果不输入`AutoReleaseTime`参数，表示取消自动释放，专有宿主机在预约时间点不再自动释放。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|请求ID。 |

## 示例

请求示例

```
http(s)://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAutoReleaseTime
&DedicatedHostId=dh-bp165p6xk2tlw61e****
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyDedicatedHostAutoReleaseTimeResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</ModifyDedicatedHostAutoReleaseTimeResponse>
```

`JSON` 格式

```
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParameter|DedicatedHostId should not be null.|参数DedicatedHostId不能为空。|
|400|InvalidAutoReleaseTime.Malformed|The specified paramter autoReleaseTime is not valid.|自动释放格式错误。请您按照ISO8601标准表示，并需要使用UTC时间，格式为：yyyy-MM-ddTHH:mm:ssZ。|
|500|InternalError|The request processing has failed due to some unknown error, exception or failure.|内部错误，请重试。如果多次尝试失败，请提交工单。|
|400|UnsupportedParameter|The parameters is unsupported.|指定的参数不合法。|
|403|ChargeTypeViolation|The operation is not permitted due to charge type of the dedicated host.|专有宿主机的付费方式不支持该操作，请您检查专有宿主机的付费类型是否与该操作冲突。|
|404|NoSuchResource|The specified resource is not found.|指定的资源不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Ecs)查看更多错误码。

