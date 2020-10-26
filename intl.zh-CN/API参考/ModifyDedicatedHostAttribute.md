# ModifyDedicatedHostAttribute

调用ModifyDedicatedHostAttribute修改一台专有宿主机的部分信息，包括专有宿主机的名称、描述和服务不可用属性等。

## 接口说明

-   修改CPU超卖比时，专有宿主机上的ECS实例必须为已停止（`Stopped`）状态。
-   修改CPU超卖比不会影响DDH的运行状态，但需注意DDH中已分配的vCPU数量不能超过修改后的总vCPU数量，否则超出部分的ECS实例将无法启动。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostAttribute&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDedicatedHostAttribute|系统规定参数。取值：ModifyDedicatedHostAttribute |
|DedicatedHostId|String|是|dh-bp165p6xk2tlw61e\*\*\*\*|专有宿主机ID。 |
|RegionId|String|是|cn-hangzhou|专有宿主机所属的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|DedicatedHostName|String|否|testDedicatedHostName|专有宿主机名称。长度为2~128个英文或中文字符。必须以大小字母或中文开头，不能以http://和https://开头。可以包含数字、半角冒号（:）、下划线（\_）或者连字符（-）。 |
|Description|String|否|testDescription|专有宿主机的描述。长度为2~256个英文或中文字符，不能以http://和https://开头。 |
|ActionOnMaintenance|String|否|Migrate|当专有宿主机发生故障或者在线修复时，为其所宿实例设置迁移方案。取值范围：

 -   Migrate：迁移实例到其他物理机并重新启动实例。
-   Stop：在当前专有宿主机上停止实例，确认无法修复专有宿主机后，迁移实例到其他物理机并重新启动实例。

 当专有宿主机上挂载的是云盘时，默认值：Migrate。

 当专有宿主机上挂载的是本地盘时，默认值：Stop。 |
|NetworkAttributes.SlbUdpTimeout|Integer|否|60|负载均衡连接的UDP会话超时时间，单位：秒。取值范围：15~310 |
|NetworkAttributes.UdpTimeout|Integer|否|60|为专有宿主机上运行的云服务设置用户访问的UDP会话超时时间，单位：秒。取值范围：15~310 |
|AutoPlacement|String|否|on|设置专有宿主机是否加入自动部署资源池。当您在专有宿主机上创建实例，却不指定**DedicatedHostId**时，阿里云自动从资源池中选取专有宿主机放置实例。取值范围：

 -   on：加入自动部署资源池。
-   off：不加入自动部署资源池。

 自动部署功能详情，请参见[功能特性](~~118938~~)。 |
|DedicatedHostClusterId|String|否|dc-bp165p6xk2tlw61e\*\*\*\*|专有宿主机集群ID。 |
|CpuOverCommitRatio|Float|否|1|CPU超卖比。仅自定义规格g6s、c6s、r6s支持设置CPU超卖比。取值范围：1~5

 CPU超卖比影响DDH的可用vCPU数，一台DDH的可用vCPU数=物理CPU核数\*2\*CPU超卖比。例如，g6s的物理CPU核数为52，如果设置CPU超卖比为4，则DDH创建完成后vCPU总数显示为412。针对CPU绝对稳定性要求不严苛或者CPU负载不高的场景，例如开发测试环境，提升超卖比可以提升可用vCPU数，用于部署更多同等规格的ECS实例，降低单位部署成本。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|2A4EA075-CB5B-41B7-B0EB-70D339F64DE7|请求ID。 |

## 示例

请求示例

```
http(s)://ecs.aliyuncs.com/?Action=ModifyDedicatedHostAttribute
&DedicatedHostId=dh-bp165p6xk2tlw61e****
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyDedicatedHostAttributeResponse>
    <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</ModifyDedicatedHostAttributeResponse>
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
|404|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|指定的专有宿主机不存在。|
|400|InvalidDedicatedHostName.Malformed|The specified parameter DedicatedHostName is not valid.|指定的参数DedicatedHostName无效。|
|400|InvalidDescription.Malformed|The specified parameter Description is not valid.|指定的资源描述格式不合法。长度为2-256个字符，不能以http://和https://开头。|
|403|InvalidUser.Unauthorized|The user is not authorized|您当前使用的账号无权限。|
|400|InvalidParameter.SlbUdpTimeout|The specified value is invalid.|指定的参数SlbUdpTimeout无效。|
|400|InvalidParameter.UdpTimeout|The specified value is invalid.|指定的参数UdpTimeout无效。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Ecs)查看更多错误码。

