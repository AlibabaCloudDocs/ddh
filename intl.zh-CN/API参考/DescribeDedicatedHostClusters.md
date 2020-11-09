# DescribeDedicatedHostClusters

调用DescribeDedicatedHostClusters查询一个或多个专有宿主机集群的详细信息。

## 接口说明

请求参数的作用类似于一个过滤器，过滤器为逻辑与（AND）关系。如果某一参数为空，则过滤器不起作用。但是参数`DedicatedHostClusterIds`的值如果是一个空JSON数组，即`[]`，则视为该过滤器有效，且返回值为空。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=DescribeDedicatedHostClusters&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDedicatedHostClusters|系统规定参数。取值：DescribeDedicatedHostClusters |
|RegionId|String|是|cn-hangzhou|专有宿主机集群所在的地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|Tag.N.Key|String|否|TestKey|专有宿主机集群的标签键。N的取值范围：1~20。一旦传入该值，则不允许为空字符串。最多支持64个字符，不能以`aliyun`和`acs:`开头，不能包含`http://`或`https://`。

 使用一个标签过滤资源，查询到该标签下的资源数量不能超过1000个；使用多个标签过滤资源，查询到同时绑定了多个标签的资源数量不能超过1000个。如果资源数量超过1000个，请使用[ListTagResources](~~110425~~)接口进行查询。 |
|Tag.N.Value|String|否|TestValue|专有宿主机集群的标签值。N的取值范围：1~20。一旦传入该值，则不允许为空字符串。最多支持64个字符，不能以`aliyun`和`acs:`开头，不能包含`http://`或`https://`。 |
|ResourceGroupId|String|否|rg-bp67acfmxazb4p\*\*\*\*|专有宿主机集群要加入的资源组ID。使用该参数过滤资源时，资源数量不能超过1000个。 |
|ZoneId|String|否|cn-hangzhou-f|专有宿主机集群所在的可用区ID。您可以调用[DescribeZones](~~25610~~)查看阿里云地域下的可用区。 |
|DedicatedHostClusterIds|String|否|\["dc-bp12wlf6am0vz9v2\*\*\*\*", "dc-bp12wlf6am0vz9v3\*\*\*\*"\]|专有宿主机集群ID列表。取值可以由多个专有宿主机集群ID组成一个JSON数组，格式为`["dc-xxxxxxxxx", "dc-yyyyyyyyy", … "dc-zzzzzzzzz"]`。支持最多100个ID，用半角逗号字符隔开。 |
|DedicatedHostClusterName|String|否|myDDHCluster|专有宿主机集群名称。 |
|PageNumber|Integer|否|1|专有宿主机集群状态列表的页码。

 起始值：1

 默认值：1 |
|PageSize|Integer|否|5|分页查询时设置的每页行数。

 最大值：100

 默认值：10 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DedicatedHostClusters|Array of DedicatedHostCluster| |由一个或多个专有宿主机集群状态组成的数组。 |
|DedicatedHostCluster| | | |
|DedicatedHostClusterCapacity|Struct| |专有宿主机集群容量。 |
|AvailableMemory|Integer|4|当前可用内存大小。单位：GiB |
|AvailableVcpus|Integer|2|当前可用vCPU数。 |
|LocalStorageCapacities|Array of LocalStorageCapacity| |本地存储容量。 |
|LocalStorageCapacity| | | |
|AvailableDisk|Integer|20|当前可用本地盘大小。单位：GiB |
|DataDiskCategory|String|cloud|数据盘类型。可能值：

 -   cloud：普通云盘
-   cloud\_efficiency：高效云盘
-   cloud\_ssd：SSD云盘
-   ephemeral\_ssd：本地SSD盘
-   cloud\_essd：ESSD云盘 |
|TotalDisk|Integer|40|本地盘总大小。单位：GiB |
|TotalMemory|Integer|8|总内存大小。单位：GiB |
|TotalVcpus|Integer|4|总vCPU数。 |
|DedicatedHostClusterId|String|dc-bp12wlf6am0vz9v2\*\*\*\*|专有宿主机集群ID。 |
|DedicatedHostClusterName|String|myDDHCluster|专有宿主机集群名称。 |
|DedicatedHostIds|List|\["dh-bp181e5064b5sotr\*\*\*\*","dh-bp18064b5sotrr9c\*\*\*\*"\]|由DedicatedHostId组成的集合，返回专有宿主机集群下的专有宿主机ID列表。 |
|Description|String|This-is-my-DDHCluster|专有宿主机集群描述。 |
|RegionId|String|cn-hangzhou|专有宿主机集群所在的地域ID。 |
|ResourceGroupId|String|rg-bp67acfmxazb4p\*\*\*\*|专有宿主机集群的资源组ID。 |
|Tags|Array of Tag| |专有宿主机集群的标签。 |
|Tag| | | |
|TagKey|String|TestKey|专有宿主机集群的标签键。 |
|TagValue|String|TestValue|专有宿主机集群的标签值。 |
|ZoneId|String|cn-hangzhou-f|专有宿主机集群所在的可用区ID。 |
|PageNumber|Integer|1|专有宿主机集群状态列表的页码。 |
|PageSize|Integer|5|输入时设置的每页行数。 |
|RequestId|String|214A2187-B06F-4E49-A081-4D053466A8C7|请求ID。 |
|TotalCount|Integer|2|专有宿主机总个数。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostClusters
&RegionId=cn-hangzhou
&ZoneId=cn-hangzhou-f
&DedicatedHostClusterName=myDDHCluster
&PageNumber=1
&PageSize=5
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDedicatedHostClustersResponse>
      <DedicatedHostClusters>
            <DedicatedHostCluster>
                  <Description>This-is-my-DDHCluster</Description>
                  <ZoneId>cn-hangzhou-f</ZoneId>
                  <DedicatedHostClusterName>myDDHCluster</DedicatedHostClusterName>
                  <ResourceGroupId>rg-bp67acfmxazb4p****</ResourceGroupId>
                  <DedicatedHostClusterCapacity>
                        <TotalMemory>0</TotalMemory>
                        <AvailableMemory>0</AvailableMemory>
                        <AvailableVcpus>0</AvailableVcpus>
                        <TotalVcpus>0</TotalVcpus>
                        <LocalStorageCapacities>
                </LocalStorageCapacities>
                  </DedicatedHostClusterCapacity>
                  <RegionId>cn-hangzhou</RegionId>
                  <DedicatedHostIds>
            </DedicatedHostIds>
                  <DedicatedHostClusterId>dc-bp1i7d8p4ku9jgob****</DedicatedHostClusterId>
            </DedicatedHostCluster>
      </DedicatedHostClusters>
      <TotalCount>1</TotalCount>
      <RequestId>502C9C44-B851-44F4-8805-3EC15E726745</RequestId>
      <PageSize>10</PageSize>
      <PageNumber>1</PageNumber>
</DescribeDedicatedHostClustersResponse>
```

`JSON` 格式

```
{
	"DedicatedHostClusters": {
		"DedicatedHostCluster": [
			{
				"Description": "This-is-my-DDHCluster",
				"ZoneId": "cn-hangzhou-f",
				"DedicatedHostClusterName": "myDDHCluster",
				"ResourceGroupId": "rg-bp67acfmxazb4p****",
				"DedicatedHostClusterCapacity": {
					"TotalMemory": 0,
					"AvailableMemory": 0,
					"AvailableVcpus": 0,
					"TotalVcpus": 0,
					"LocalStorageCapacities": {
						"LocalStorageCapacity": []
					}
				},
				"RegionId": "cn-hangzhou",
				"DedicatedHostIds": {
					"DedicatedHostId": []
				},
				"DedicatedHostClusterId": "dc-bp1i7d8p4ku9jgob****"
			}
		]
	},
	"TotalCount": 1,
	"RequestId": "502C9C44-B851-44F4-8805-3EC15E726745",
	"PageSize": 10,
	"PageNumber": 1
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|MissingParamter.RegionId|The regionId should not be null.|参数RegionId不得为空。|
|400|InvalidRegion.NotFound|The specified parameter RegionId is not valid.|RegionId参数不合法。|
|400|InvalidZone.NotFound|The specified parameter ZoneId is not valid.|指定的ZoneId不合法。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Ecs)查看更多错误码。

