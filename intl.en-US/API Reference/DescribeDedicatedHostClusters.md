# DescribeDedicatedHostClusters

You can call this operation to query details of one or more dedicated host clusters.

## Description

You can specify multiple request parameters to be queried. Specified parameters have logical AND relations. Only the specified parameters are included in the filter conditions. However, if `DedicatedHostClusterIds` is set to an empty JSON array \(`[]`\), it is regarded as an effective filter condition and an empty result is returned.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=DescribeDedicatedHostClusters&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDedicatedHostClusters|The operation that you want to perform. Set the value to DescribeDedicatedHostClusters. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host cluster. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |
|Tag.N.Key|String|No|TestKey|The key of tag N of the dedicated host cluster. Valid values of N: 1 to 20. The tag key cannot be an empty string. It can be up to 64 characters in length and cannot start with `acs:` or `aliyun`. It cannot contain `http://` or `https://`.

If a single tag is specified to query resources, up to 1,000 resources that are bound with this tag can be displayed in the response. If multiple tags are specified to query resources, up to 1,000 resources that are bound with all these tags can be displayed in the response. To query more than 1,000 resources that are bound with specified tags, call the [ListTagResources](~~110425~~) operation. |
|Tag.N.Value|String|No|TestValue|The value of tag N of the dedicated host cluster. Valid values of N: 1 to 20. The tag value cannot be an empty string. It can be up to 64 characters in length and cannot start with `acs:` or `aliyun`. It cannot contain `http://` or `https://`. |
|ResourceGroupId|String|No|rg-bp67acfmxazb4p\*\*\*\*|The ID of the resource group to which the dedicated host cluster belongs. If this parameter is specified to query resources, up to 1,000 resources that belong to the specified resource group can be displayed in the response. |
|ZoneId|String|No|cn-hangzhou-f|The zone ID of the dedicated host cluster. You can call the [DescribeZones](~~25610~~) operation to query the most recent zone list. |
|DedicatedHostClusterIds|String|No|\["dc-bp12wlf6am0vz9v2\*\*\*\*", "dc-bp12wlf6am0vz9v3\*\*\*\*"\]|The IDs of dedicated host clusters. The value can be a JSON array that consists of up to 100 dedicated host cluster IDs in the format of `["dc-xxxxxxxxx", "dc-yyyyyyyyy", ... "dc-zzzzzzzzz"]`. Separate the IDs with commas \(,\). |
|DedicatedHostClusterName|String|No|myDDHCluster|The name of the dedicated host cluster. |
|PageNumber|Integer|No|1|The number of the page to return.

Pages start from page 1.

Default: 1 |
|PageSize|Integer|No|5|The number of entries to return on each page.

Valid values: 1 to 100

Default value: 10 |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DedicatedHostClusters|Array of DedicatedHostCluster| |Details about the dedicated host clusters. |
|DedicatedHostCluster| | | |
|DedicatedHostClusterCapacity|Struct| |The capacity of the dedicated host cluster. |
|AvailableMemory|Integer|4|The available memory size. Unit: GiB. |
|AvailableVcpus|Integer|2|The number of available vCPUs. |
|LocalStorageCapacities|Array of LocalStorageCapacity| |The local storage. |
|LocalStorageCapacity| | | |
|AvailableDisk|Integer|20|The available capacity of the local disk. Unit: GiB. |
|DataDiskCategory|String|cloud|The category of the data disk. Valid values:

-   cloud: basic disk
-   cloud\_efficiency: ultra disk
-   cloud\_ssd: standard SSD
-   ephemeral\_ssd: local SSD
-   cloud\_essd: enhanced SSD \(ESSD\) |
|TotalDisk|Integer|40|The total capacity of the local disk. Unit: GiB. |
|TotalMemory|Integer|8|The total memory size. Unit: GiB. |
|TotalVcpus|Integer|4|The total number of vCPUs. |
|DedicatedHostClusterId|String|dc-bp12wlf6am0vz9v2\*\*\*\*|The ID of the dedicated host cluster. |
|DedicatedHostClusterName|String|myDDHCluster|The name of the dedicated host cluster. |
|DedicatedHostIds|List|\["dh-bp181e5064b5sotr\*\*\*\*","dh-bp18064b5sotrr9c\*\*\*\*"\]|The IDs of dedicated hosts in the dedicated host cluster. |
|Description|String|This-is-my-DDHCluster|The description of the dedicated host cluster. |
|RegionId|String|cn-hangzhou|The region ID of the dedicated host cluster. |
|ResourceGroupId|String|rg-bp67acfmxazb4p\*\*\*\*|The ID of the resource group to which the dedicated host cluster belongs. |
|Tags|Array of Tag| |The tags of the dedicated host cluster. |
|Tag| | | |
|TagKey|String|TestKey|The tag key of the dedicated host cluster. |
|TagValue|String|TestValue|The tag value of the dedicated host cluster. |
|ZoneId|String|cn-hangzhou-f|The zone ID of the dedicated host cluster. |
|PageNumber|Integer|1|The page number of the returned page. |
|PageSize|Integer|5|The number of entries returned per page. |
|RequestId|String|214A2187-B06F-4E49-A081-4D053466A8C7|The ID of the request. |
|TotalCount|Integer|2|The total number of dedicated host clusters. |

## Examples

Sample requests

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHostClusters
&RegionId=cn-hangzhou
&ZoneId=cn-hangzhou-f
&DedicatedHostClusterName=myDDHCluster
&PageNumber=1
&PageSize=5
&<Common request parameters>
```

Sample success responses

`XML` format

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

`JSON` format

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

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|MissingParamter.RegionId|The regionId should not be null.|The error message returned because the required RegionId parameter is not specified.|
|400|InvalidRegion.NotFound|The specified parameter RegionId is not valid.|The error message returned because the specified RegionId parameter is invalid.|
|400|InvalidZone.NotFound|The specified parameter ZoneId is not valid.|The error message returned because the specified ZoneId parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

