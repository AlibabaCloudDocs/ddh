# DescribeDedicatedHostTypes

调用DescribeDedicatedHostTypes查询指定地域下支持的专有宿主机规格详细参数，或者查询专有宿主机支持的ECS实例规格族。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Ecs&api=DescribeDedicatedHostTypes&type=RPC&version=2014-05-26)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeDedicatedHostTypes|系统规定参数。取值：DescribeDedicatedHostTypes |
|RegionId|String|是|cn-hangzhou|专有宿主机所在地域ID。您可以调用[DescribeRegions](~~25609~~)查看最新的阿里云地域列表。 |
|DedicatedHostType|String|否|ddh.sn1ne|专有宿主机规格。更多详情，请参见[宿主机规格](~~68564~~)。 |
|SupportedInstanceTypeFamily|String|否|ecs.sn1ne|专有宿主机规格支持的ECS实例规格族。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|DedicatedHostTypes|Array of DedicatedHostType| |返回专有宿主机规格的信息。 |
|DedicatedHostType| | | |
|Cores|Integer|2|单个物理CPU的核数。 |
|CpuOverCommitRatioRange|String|1-5|支持设置CPU超卖比的范围。 |
|DedicatedHostType|String|ddh.sn1ne|专有宿主机规格类型。如果您需要使用更多专有宿主机规格，可以提交工单联系阿里云。 |
|GPUSpec|String|gpu|GPU型号。 |
|LocalStorageAmount|Integer|0|专有宿主机上的本地盘数量。 |
|LocalStorageCapacity|Long|0|一块本地盘容量，单位：GiB。 |
|LocalStorageCategory|String|local|本地盘类型。 |
|MemorySize|Float|112.0|内存容量，单位：GiB。 |
|PhysicalGpus|Integer|2|物理GPU数量。 |
|Sockets|Integer|2|物理处理器（CPU）数量。 |
|SupportCpuOverCommitRatio|Boolean|true|是否支持设置CPU超卖比。 |
|SupportedInstanceTypeFamilies|List|ecs.sn1ne|专有宿主机支持的ECS实例规格族。 |
|SupportedInstanceTypesList|List|ecs.sn1ne.large|专有宿主机支持的ECS实例规格。 |
|TotalVcpus|Integer|56|虚拟CPU总核数。 |
|TotalVgpus|Integer|10|虚拟GPU总核数。 |
|RequestId|String|5FE5FF06-3A33-4658-8495-6445FC54E327|请求ID。 |

## 示例

请求示例

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostTypes
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeDedicatedHostTypesResponse>
      <RequestId>E7676157-C48A-445A-BFCB-6669EDE8DA3D</RequestId>
      <DedicatedHostTypes>
            <DedicatedHostType>
                  <PhysicalGpus>0</PhysicalGpus>
                  <MemorySize>180</MemorySize>
                  <LocalStorageCapacity>0</LocalStorageCapacity>
                  <DedicatedHostType>ddh.c6s</DedicatedHostType>
                  <LocalStorageAmount>0</LocalStorageAmount>
                  <Cores>52</Cores>
                  <LocalStorageCategory></LocalStorageCategory>
                  <Sockets>2</Sockets>
                  <GPUSpec></GPUSpec>
                  <SupportedInstanceTypeFamilies>
                        <SupportedInstanceTypeFamily>ecs.ddh6s.custom</SupportedInstanceTypeFamily>
                  </SupportedInstanceTypeFamilies>
                  <TotalVgpus>0</TotalVgpus>
                  <CpuOverCommitRatioRange>1-5</CpuOverCommitRatioRange>
                  <SupportedInstanceTypesList>
            </SupportedInstanceTypesList>
                  <SupportCpuOverCommitRatio>true</SupportCpuOverCommitRatio>
                  <TotalVcpus>520</TotalVcpus>
            </DedicatedHostType>
      </DedicatedHostTypes>
</DescribeDedicatedHostTypesResponse>
```

`JSON` 格式

```
{
	"RequestId": "E7676157-C48A-445A-BFCB-6669EDE8DA3D",
	"DedicatedHostTypes": {
		"DedicatedHostType": [
			{
				"PhysicalGpus": 0,
				"MemorySize": 180,
				"LocalStorageCapacity": 0,
				"DedicatedHostType": "ddh.c6s",
				"LocalStorageAmount": 0,
				"Cores": 52,
				"LocalStorageCategory": "",
				"Sockets": 2,
				"GPUSpec": "",
				"SupportedInstanceTypeFamilies": {
					"SupportedInstanceTypeFamily": [
						"ecs.ddh6s.custom"
					]
				},
				"TotalVgpus": 0,
				"CpuOverCommitRatioRange": "1-5",
				"SupportedInstanceTypesList": {
					"SupportedInstanceTypesList": []
				},
				"SupportCpuOverCommitRatio": true,
				"TotalVcpus": 520
			}
		]
	}
}
```

## 错误码

访问[错误中心](https://error-center.aliyun.com/status/product/Ecs)查看更多错误码。

