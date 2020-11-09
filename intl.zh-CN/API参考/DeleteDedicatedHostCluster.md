# DeleteDedicatedHostCluster

调用DeleteDedicatedHostCluster删除一个专有宿主机集群。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=DeleteDedicatedHostCluster&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteDedicatedHostCluster|系统规定参数。取值：DeleteDedicatedHostCluster |
|DedicatedHostClusterId|String|是|dc-bp12wlf6am0vz9v2\*\*\*\*|专有宿主机集群ID。 |
|RegionId|String|是|cn-hangzhou|专有宿主机集群所在的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|11B55F58-D3A4-4A9B-9596-342420D02FF8|请求ID。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=DeleteDedicatedHostCluster
&RegionId=cn-hangzhou
&DedicatedHostClusterId=dc-bp12wlf6am0vz9v2****
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DeleteDedicatedHostClusterResponse>
      <RequestId>11B55F58-D3A4-4A9B-9596-342420D02FF8</RequestId>
</DeleteDedicatedHostClusterResponse>
```

`JSON` 格式

```
{
	"RequestId": "11B55F58-D3A4-4A9B-9596-342420D02FF8"
}
```

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Ecs)查看更多错误码。

