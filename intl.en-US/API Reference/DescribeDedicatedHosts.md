# DescribeDedicatedHosts

You can call this operation to query the details of one or more dedicated hosts, including the physical performance specifications, machine codes, service status, and a list of ECS instances that are created on the dedicated hosts.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates a sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=DescribeDedicatedHosts&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDedicatedHosts|The operation that you want to perform. Set the value to DescribeDedicatedHosts. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |
|ZoneId|String|No|cn-hangzhou-g|The zone ID of the dedicated host. |
|DedicatedHostIds|String|No|\["dh-bp165p6xk2tlw61e\*\*\*\*", "dh-bp1f9vxmno7emy96\*\*\*\*"\]|The IDs of the dedicated hosts. You can specify up to 100 dedicated host IDs in a single request. Separate multiple IDs with commas \(,\). |
|DedicatedHostName|String|No|MyDDHTestName|The name of the dedicated host. |
|Status|String|No|Available|The service status of the dedicated host. Valid values:

-   Available: The dedicated host is available.
-   UnderAssessment: The dedicated host has potential failures and may fail when it is used.
-   PermanentFailure: The dedicated host has permanent failures and cannot be used.

Default value: Available |
|DedicatedHostType|String|No|ddh.g5|The dedicated host type. |
|LockReason|String|No|financial|The reasons why the resources of the dedicated host were locked. Valid values:

-   financial: The resources were locked due to overdue payments.
-   security: The resources were locked for security reasons. |
|PageNumber|Integer|No|1|The number of the page to return.

Default: 1. |
|PageSize|Integer|No|10|The number of entries to return on each page. Valid values: 1 to 100.

Default value: 10 |
|Tag.N.Key|String|No|TestKey|The key of tag N of the dedicated host. Valid values of N: 1 to 20. The tag key cannot be an empty string. It can be up to 128 characters in length and cannot start with acs: or aliyun. It cannot contain http:// or https://. |
|Tag.N.Value|String|No|TestValue|The value of tag N of the dedicated host. Valid values of N: 1 to 20. The tag value can be an empty string. It can be up to 128 characters in length and cannot start with acs: or aliyun. It cannot contain http:// or https://. |
|ResourceGroupId|String|No|rg-aek3b6jzp66\*\*\*\*|The ID of the resource group to which the dedicated host belongs. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DedicatedHosts|Array of DedicatedHost| |Details about the dedicated hosts. |
|DedicatedHost| | | |
|ActionOnMaintenance|String|Migrate|The policy used to migrate the instances deployed on the dedicated host when the dedicated host fails or needs to be repaired online. Valid values:

-   Migrate: The instances are migrated to another physical server and restarted.

If the dedicated host is attached with cloud disks, the default value is Migrate.

-   Stop: The instances are stopped. If the dedicated host cannot be repaired, the instances are migrated to another physical server and restarted.

If the dedicated host is attached with local disks, the default value is Stop. |
|AutoPlacement|String|on|Indicates whether the dedicated host was added to the resource pool for automatic deployment. Valid values:

-   on: The dedicated host was added to the resource pool for automatic deployment.
-   off: The dedicated host was not added to the resource pool for automatic deployment.

For more information about automatic deployment, see [Automatic deployment](~~118938~~). |
|AutoReleaseTime|String|2017-01-01T12:00Z|The automatic release time of the dedicated host. The time follows the [ISO 8601](~~25696~~) standard in the `yyyy-MM-ddTHH:mmZ` format. The time is displayed in UTC. |
|Capacity|Struct| |The performance specifications of the dedicated host. |
|AvailableLocalStorage|Integer|65|The available space of the local disks. Unit: GiB. |
|AvailableMemory|Float|25|The available space of the memory. Unit: GiB. |
|AvailableVcpus|Integer|5|The number of available vCPUs. |
|AvailableVgpus|Integer|2|The number of available vGPUs. |
|LocalStorageCategory|String|i2|The category of the local disks. |
|TotalLocalStorage|Integer|512|The total capacity of the local disks. Unit: GiB. |
|TotalMemory|Float|1024|The total capacity of the memory. Unit: GiB. |
|TotalVcpus|Integer|56|The total number of vCPUs. |
|TotalVgpus|Integer|10|The total number of vGPUs. |
|ChargeType|String|Prepaid|The billing method of the dedicated host. |
|Cores|Integer|3|The number of physical cores in a single CPU. |
|CpuOverCommitRatio|Float|1|The CPU overcommit ratio. |
|CreationTime|String|2018-01-01T12:00Z|The time when the dedicated host was created. The time follows the [ISO 8601](~~25696~~) standard in the `yyyy-MM-ddTHH:mmZ` format. The time is displayed in UTC. |
|DedicatedHostClusterId|String|dc-bp12wlf6am0vz9v2\*\*\*\*|The ID of the dedicated host cluster to which the dedicated host belongs. |
|DedicatedHostId|String|dh-bp165p6xk2tlw61e\*\*\*\*|The ID of the dedicated host. |
|DedicatedHostName|String|MyDDHTestName|The name of the dedicated host. |
|DedicatedHostType|String|ddh.g5|The type of the dedicated host. |
|Description|String|this-is-my-DDH|The description of the dedicated host. |
|ExpiredTime|String|2019-01-01T12:00Z|The expiration time of the subscription dedicated host. The time follows the [ISO 8601](~~25696~~) standard in the `yyyy-MM-ddTHH:mmZ` format. The time is displayed in UTC. |
|GPUSpec|String|gpu|The GPU model. |
|Instances|Array of Instance| |The ECS instances that were created on the dedicated host. |
|Instance| | | |
|InstanceId|String|i-bp14ot0ykf8w13a1\*\*\*\*|The ID of the ECS instance. |
|InstanceType|String|ecs.g5.large|The instance type of the ECS instance. |
|MachineId|String|12aaa123456ff19dec12345d3026e\*\*\*\*|The machine code of the dedicated host. |
|NetworkAttributes|Struct| |The network attributes of the dedicated host. |
|SlbUdpTimeout|Integer|60|The timeout period of the UDP session that was established between Server Load Balancer \(SLB\) and the dedicated host. |
|UdpTimeout|Integer|60|The timeout period of the UDP session that was established between a user and an Alibaba Cloud service on the dedicated host. |
|OperationLocks|Array of OperationLock| |The reasons why the resources of the dedicated host were locked. |
|OperationLock| | | |
|LockReason|String|financial|The reason why the resources of the dedicated host were locked. Example value: financial. It indicates that the resources were locked due to overdue payments. |
|PhysicalGpus|Integer|10|The number of physical GPUs. |
|RegionId|String|cn-hangzhou|The region ID of the dedicated host. |
|ResourceGroupId|String|rg-aek3b6jzp66\*\*\*\*|The ID of the resource group to which the dedicated host belongs. |
|SaleCycle|String|Month|The unit of the subscription period. Valid values:

-   Month
-   Year |
|Sockets|Integer|5|The number of physical CPUs. |
|Status|String|Available|The service status of the dedicated host. Valid values:

-   Available
-   UnderAssessment
-   PermanentFailure |
|SupportedCustomInstanceTypeFamilies|List|ecs.ddh6s.custom|The custom ECS instance families supported by the dedicated host. |
|SupportedInstanceTypeFamilies|List|ecs.g5|The ECS instance families supported by the dedicated host. |
|SupportedInstanceTypesList|List|ecs.g5.large|The ECS instance types supported by the dedicated host. |
|Tags|Array of Tag| |The tags of the dedicated host. |
|Tag| | | |
|TagKey|String|TestKey|The tag key of the dedicated host. |
|TagValue|String|TestValue|The tag value of the dedicated host. |
|ZoneId|String|cn-hangzhou-g|The zone ID of the dedicated host. |
|PageNumber|Integer|5|The page number of the returned page. |
|PageSize|Integer|1|The number of entries returned per page. |
|RequestId|String|7654525A-9964-4ABB-8BCD-98F8835E809A|The ID of the request. |
|TotalCount|Integer|3|The total number of dedicated hosts. |

## Examples

Sample requests

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHosts
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDedicatedHostsResponse>
      <TotalCount>1</TotalCount>
      <DedicatedHosts>
            <DedicatedHost>
                  <PhysicalGpus>0</PhysicalGpus>
                  <MachineId>73aaa79494ff19dec79446d3026e****</MachineId>
                  <DedicatedHostId>dh-bp165p6xk2tlw61e****</DedicatedHostId>
                  <Description></Description>
                  <ResourceGroupId></ResourceGroupId>
                  <SupportedCustomInstanceTypeFamilies>
            </SupportedCustomInstanceTypeFamilies>
                  <NetworkAttributes></NetworkAttributes>
                  <GPUSpec></GPUSpec>
                  <DedicatedHostName>MyDDHTestName</DedicatedHostName>
                  <Capacity>
                        <AvailableVgpus>0</AvailableVgpus>
                        <LocalStorageCategory></LocalStorageCategory>
                        <TotalVgpus>0</TotalVgpus>
                        <TotalMemory>768</TotalMemory>
                        <AvailableMemory>768</AvailableMemory>
                        <AvailableVcpus>104</AvailableVcpus>
                        <TotalVcpus>104</TotalVcpus>
                        <AvailableLocalStorage>0</AvailableLocalStorage>
                        <TotalLocalStorage>0</TotalLocalStorage>
                  </Capacity>
                  <ExpiredTime>2999-09-08T16:00Z</ExpiredTime>
                  <SaleCycle></SaleCycle>
                  <Status>Available</Status>
                  <ZoneId>cn-hangzhou-h</ZoneId>
                  <AutoPlacement>on</AutoPlacement>
                  <DedicatedHostType>ddh.r6</DedicatedHostType>
                  <OperationLocks>
            </OperationLocks>
                  <Cores>52</Cores>
                  <Instances>
            </Instances>
                  <Sockets>2</Sockets>
                  <ChargeType>PostPaid</ChargeType>
                  <SupportedInstanceTypeFamilies>
                        <SupportedInstanceTypeFamily>ecs.c6</SupportedInstanceTypeFamily>
                        <SupportedInstanceTypeFamily>ecs.g6</SupportedInstanceTypeFamily>
                        <SupportedInstanceTypeFamily>ecs.ic6</SupportedInstanceTypeFamily>
                        <SupportedInstanceTypeFamily>ecs.r6</SupportedInstanceTypeFamily>
                  </SupportedInstanceTypeFamilies>
                  <ActionOnMaintenance>Migrate</ActionOnMaintenance>
                  <CreationTime>2020-04-15T07:12Z</CreationTime>
                  <RegionId>cn-hangzhou</RegionId>
                  <SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.26xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.3xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.2xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.13xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.6xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.4xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.16xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.13xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.26xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.26xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.3xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.13xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.16xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.4xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.16xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.6xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6.large</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.2xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.2xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.3xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.6xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.4xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6.large</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.large</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.4xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.3xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.6xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.2xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.ic6.large</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6-dbeni.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6nv.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.c6vn.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.r6vn.8xlarge</SupportedInstanceTypesList>
                        <SupportedInstanceTypesList>ecs.g6-nfveni.large</SupportedInstanceTypesList>
                  </SupportedInstanceTypesList>
                  <DedicatedHostClusterId></DedicatedHostClusterId>
                  <AutoReleaseTime></AutoReleaseTime>
            </DedicatedHost>
      </DedicatedHosts>
      <RequestId>9E9354D4-C89E-4A82-A70E-3EEAD6007885</RequestId>
      <PageSize>10</PageSize>
      <PageNumber>1</PageNumber>
</DescribeDedicatedHostsResponse>
```

`JSON` format

```
{
    "TotalCount": 1,
    "DedicatedHosts": {
        "DedicatedHost": [
            {
                "PhysicalGpus": 0,
                "MachineId": "73aaa79494ff19dec79446d3026e****",
                "DedicatedHostId": "dh-bp165p6xk2tlw61e****",
                "Description": "",
                "ResourceGroupId": "",
                "SupportedCustomInstanceTypeFamilies": {
                    "SupportedCustomInstanceTypeFamily": []
                },
                "NetworkAttributes": {},
                "GPUSpec": "",
                "DedicatedHostName": "MyDDHTestName",
                "Capacity": {
                    "AvailableVgpus": 0,
                    "LocalStorageCategory": "",
                    "TotalVgpus": 0,
                    "TotalMemory": 768,
                    "AvailableMemory": 768,
                    "AvailableVcpus": 104,
                    "TotalVcpus": 104,
                    "AvailableLocalStorage": 0,
                    "TotalLocalStorage": 0
                },
                "ExpiredTime": "2999-09-08T16:00Z",
                "SaleCycle": "",
                "Status": "Available",
                "ZoneId": "cn-hangzhou-h",
                "AutoPlacement": "on",
                "DedicatedHostType": "ddh.r6",
                "OperationLocks": {
                    "OperationLock": []
                },
                "Cores": 52,
                "Instances": {
                    "Instance": []
                },
                "Sockets": 2,
                "ChargeType": "PostPaid",
                "SupportedInstanceTypeFamilies": {
                    "SupportedInstanceTypeFamily": [
                        "ecs.c6",
                        "ecs.g6",
                        "ecs.ic6",
                        "ecs.r6"
                    ]
                },
                "ActionOnMaintenance": "Migrate",
                "CreationTime": "2020-04-15T07:12Z",
                "RegionId": "cn-hangzhou",
                "SupportedInstanceTypesList": {
                    "SupportedInstanceTypesList": [
                        "ecs.g6.26xlarge",
                        "ecs.g6.3xlarge",
                        "ecs.g6.8xlarge",
                        "ecs.g6.2xlarge",
                        "ecs.g6.13xlarge",
                        "ecs.g6.6xlarge",
                        "ecs.c6.8xlarge",
                        "ecs.g6.4xlarge",
                        "ecs.g6.xlarge",
                        "ecs.g6.16xlarge",
                        "ecs.c6.13xlarge",
                        "ecs.c6.26xlarge",
                        "ecs.r6.xlarge",
                        "ecs.r6.26xlarge",
                        "ecs.r6.3xlarge",
                        "ecs.r6.13xlarge",
                        "ecs.r6.16xlarge",
                        "ecs.r6.4xlarge",
                        "ecs.c6.16xlarge",
                        "ecs.r6.6xlarge",
                        "ecs.g6.large",
                        "ecs.c6.2xlarge",
                        "ecs.r6.2xlarge",
                        "ecs.c6.xlarge",
                        "ecs.c6.3xlarge",
                        "ecs.c6.6xlarge",
                        "ecs.c6.4xlarge",
                        "ecs.c6.large",
                        "ecs.r6.large",
                        "ecs.r6.8xlarge",
                        "ecs.ic6.4xlarge",
                        "ecs.ic6.8xlarge",
                        "ecs.ic6.xlarge",
                        "ecs.ic6.3xlarge",
                        "ecs.ic6.6xlarge",
                        "ecs.ic6.2xlarge",
                        "ecs.ic6.large",
                        "ecs.r6-dbeni.8xlarge",
                        "ecs.g6nv.8xlarge",
                        "ecs.c6vn.8xlarge",
                        "ecs.r6vn.8xlarge",
                        "ecs.g6-nfveni.large"
                    ]
                },
                "DedicatedHostClusterId": "",
                "AutoReleaseTime": ""
            }
        ]
    },
    "RequestId": "9E9354D4-C89E-4A82-A70E-3EEAD6007885",
    "PageSize": 10,
    "PageNumber": 1
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InvalidStatus.ValueNotSupported|The pecified dedicated host status is not supported.|The error message returned because the operation is not supported while the dedicated host is in the current state.|
|400|MissingParamter.RegionId|The regionId should not be null.|The error message returned because the required RegionId parameter is not specified.|
|403|InvalidDedicatedHostIds.Malformed|The amount of specified dedicatedHostIds exceeds the limit.|The error message returned because more than 100 dedicated host IDs are specified in the DedicatedHostIds value.|
|400|InvalidParameter.DedicatedHostIds|The specified parameter dedicatedHostIds is not valid.|The error message returned because the specified DedicatedHostIds parameter is invalid.|
|400|InvalidRegion.NotFound|The specified parameter RegionId is not valid.|The error message returned because the specified RegionId parameter is invalid.|
|400|InvalidZone.NotFound|The specified parameter ZoneId is not valid.|The error message returned because the specified ZoneId parameter is invalid.|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|The error message returned because the specified LockReason parameter does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

