# CreateDedicatedHostCluster

调用CreateDedicatedHostCluster创建一个专有宿主机集群。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=CreateDedicatedHostCluster&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateDedicatedHostCluster|系统规定参数。取值：CreateDedicatedHostCluster |
|RegionId|String|是|cn-hangzhou|专有宿主机集群所在的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|DryRun|Boolean|否|false|是否只预检此次请求。取值范围：

 -   true：发送检查请求，不会查询资源状况。检查项包括AccessKey是否有效、RAM用户的授权情况和是否填写了必需参数。如果检查不通过，则返回对应错误。如果检查通过，会返回错误码`DryRunOperation`。
-   false：发送正常请求，通过检查后返回2XX HTTP状态码并直接查询资源状况。

 默认值：false |
|Tag.N.Key|String|否|TestKey|专有宿主机集群的标签键。N的取值范围：1~20。一旦传入该值，则不允许为空字符串。最多支持64个字符，不能以`aliyun`和`acs:`开头，不能包含`http://`或`https://`。 |
|Tag.N.Value|String|否|TestValue|专有宿主机集群的标签值。N的取值范围：1~20。一旦传入该值，则不允许为空字符串。最多支持64个字符，不能以`aliyun`和`acs:`开头，不能包含`http://`或`https://`。 |
|ResourceGroupId|String|否|rg-bp67acfmxazb4p\*\*\*\*|专有宿主机集群要加入的资源组ID。 |
|ZoneId|String|否|cn-hangzhou-f|专有宿主机集群所在的可用区ID。您可以调用[DescribeZones](~~25610~~)查看阿里云地域下的可用区。 |
|DedicatedHostClusterName|String|否|myDDHCluster|专有宿主机集群的名称。长度为2~128个英文或中文字符，必须以大小字母或中文开头，可包含数字、英文句号（.）、下划线（\_）或连字符（-）。不能包含`http://`和`https://`。

 默认值：空 |
|Description|String|否|This-is-my-DDHCluster|专有宿主机集群的描述。长度为2~256个字符。不能以`http://`和`https://`开头。

 默认值：空 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DedicatedHostClusterId|String|dc-bp12wlf6bw0vz9v2\*\*\*\*|专有宿主机集群ID。 |
|RequestId|String|E2A664A6-2933-4C64-88AE-5033D003EADF|请求ID。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=CreateDedicatedHostCluster
&RegionId=cn-hangzhou
&ZoneId=cn-hangzhou-f
&DedicatedHostClusterName=myDDHCluster
&Description=This-is-my-DDHCluster
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<CreateDedicatedHostClusterResponse>
      <RequestId>214A2187-B06F-4E49-A081-4D053466A8C7</RequestId>
      <DedicatedHostClusterId>dc-bp12wlf6bw0vz9v2****</DedicatedHostClusterId>
</CreateDedicatedHostClusterResponse>
```

`JSON` 格式

```
{
	"RequestId": "214A2187-B06F-4E49-A081-4D053466A8C7",
	"DedicatedHostClusterId": "dc-bp12wlf6bw0vz9v2****"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|InvalidResourceGroup.NotFound|The ResourceGroup provided does not exist in our records.|资源组并不在记录中。|
|400|InvalidTagKey.Malformed|The specified Tag.n.Key is not valid.|指定的标签键参数有误。|
|400|InvalidTagValue.Malformed|The specified Tag.n.Value is not valid.|指定的标签值参数有误。|
|400|Duplicate.TagKey|The Tag.N.Key contain duplicate key.|标签中存在重复的键，请保持键的唯一性。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Ecs)查看更多错误码。

