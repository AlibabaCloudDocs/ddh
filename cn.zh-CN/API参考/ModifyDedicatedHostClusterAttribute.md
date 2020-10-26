# ModifyDedicatedHostClusterAttribute

调用ModifyDedicatedHostClusterAttribute修改一台专有宿主机集群的部分信息，包括专有宿主机集群的名称、描述信息、属性等。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostClusterAttribute&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyDedicatedHostClusterAttribute|系统规定参数。取值：ModifyDedicatedHostClusterAttribute |
|DedicatedHostClusterId|String|是|dc-bp12wlf6am0vz9v2\*\*\*\*|专有宿主机集群ID。 |
|RegionId|String|是|cn-hangzhou|专有宿主机集群所在的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|DedicatedHostClusterName|String|否|newClusterName|专有宿主机集群的名称。长度为2~128个英文或中文字符，必须以大小字母或中文开头，可包含数字、英文句号（.）、下划线（\_）或连字符（-）。不能包含`http://`和`https://`。 |
|Description|String|否|newClusterDescription|专有宿主机集群的描述。长度为2~256个字符。不能以`http://`和`https://`开头。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|11B55F58-D3A4-4A9B-9596-342420D02FF8|请求ID。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=ModifyDedicatedHostClusterAttribute
&RegionId=cn-hangzhou
&DedicatedHostClusterId=dc-bp12wlf6am0vz9v2****
&DedicatedHostClusterName=newClusterName
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<ModifyDedicatedHostClusterAttributeResponse>
      <RequestId>11B55F58-D3A4-4A9B-9596-342420D02FF8</RequestId>
</ModifyDedicatedHostClusterAttributeResponse>
```

`JSON` 格式

```
{
	"RequestId": "11B55F58-D3A4-4A9B-9596-342420D02FF8"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidDescription.Malformed|The specified parameter Description is not valid.|指定的资源描述格式不合法。长度为2-256个字符，不能以http://和https://开头。|
|403|InvalidUser.Unauthorized|The user is not authorized|您当前使用的账号无权限。|

访问[错误中心](https://error-center.aliyun.com/status/product/Ecs)查看更多错误码。

