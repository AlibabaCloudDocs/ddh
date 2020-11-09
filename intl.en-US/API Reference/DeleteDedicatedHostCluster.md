# DeleteDedicatedHostCluster

You can call this operation to delete a dedicated host cluster.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=DeleteDedicatedHostCluster&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DeleteDedicatedHostCluster|The operation that you want to perform. Set the value to DeleteDedicatedHostCluster. |
|DedicatedHostClusterId|String|Yes|dc-bp12wlf6am0vz9v2\*\*\*\*|The ID of the dedicated host cluster. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host cluster. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|11B55F58-D3A4-4A9B-9596-342420D02FF8|The ID of the request. |

## Examples

Sample requests

```
https://ecs.aliyuncs.com/?Action=DeleteDedicatedHostCluster
&RegionId=cn-hangzhou
&DedicatedHostClusterId=dc-bp12wlf6am0vz9v2****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DeleteDedicatedHostClusterResponse>
      <RequestId>11B55F58-D3A4-4A9B-9596-342420D02FF8</RequestId>
</DeleteDedicatedHostClusterResponse>
```

`JSON` format

```
{
	"RequestId": "11B55F58-D3A4-4A9B-9596-342420D02FF8"
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

