# DescribeDedicatedHostTypes

You can call this operation to query the details about dedicated host types supported in a region, or the ECS instance families supported by a specific dedicated host type.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates a sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=DescribeDedicatedHostTypes&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDedicatedHostTypes|The operation that you want to perform. Set the value to DescribeDedicatedHostTypes. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |
|DedicatedHostType|String|No|ddh.sn1ne|The dedicated host type. For more information, see [Dedicated host types](~~68564~~). |
|SupportedInstanceTypeFamily|String|No|ecs.sn1ne|The ECS instance family supported by the dedicated host type. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DedicatedHostTypes|Array of DedicatedHostType| |The information about the dedicated host type. |
|DedicatedHostType| | | |
|Cores|Integer|2|The number of cores in a single physical CPU. |
|CpuOverCommitRatioRange|String|1-5|The supported CPU overcommit ratio range. |
|DedicatedHostType|String|ddh.sn1ne|The type of the dedicated host. You can submit a ticket to request more dedicated host types. |
|GPUSpec|String|gpu|The GPU model. |
|LocalStorageAmount|Integer|0|The number of local disks on a dedicated host. |
|LocalStorageCapacity|Long|0|The capacity of a local disk. Unit: GiB. |
|LocalStorageCategory|String|local|The category of the local disks. |
|MemorySize|Float|112.0|The size of the memory. Unit: GiB. |
|PhysicalGpus|Integer|2|The number of physical GPUs. |
|Sockets|Integer|2|The number of physical CPUs. |
|SupportCpuOverCommitRatio|Boolean|true|Indicates whether the CPU overcommit ratio setting is supported. |
|SupportedInstanceTypeFamilies|List|ecs.sn1ne|The ECS instance families supported by the dedicated host. |
|SupportedInstanceTypesList|List|ecs.sn1ne.large|The ECS instance types supported by the dedicated host. |
|TotalVcpus|Integer|56|The total number of vCPUs. |
|TotalVgpus|Integer|10|The total number of vGPUs. |
|RequestId|String|5FE5FF06-3A33-4658-8495-6445FC54E327|The ID of the request. |

## Examples

Sample requests

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostTypes
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

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

`JSON` format

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

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

