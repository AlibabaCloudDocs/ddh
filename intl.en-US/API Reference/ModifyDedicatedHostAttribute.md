# ModifyDedicatedHostAttribute

You can call this operation to modify some attributes of a dedicated host, such as the name, description, and instance migration policy that is applied when the dedicated host fails.

## Description

-   All the ECS instances that are hosted on a dedicated host must be in the Stopped \(`Stopped`\) state before you can modify the CPU overcommit ratio of the dedicated host.
-   Modifications to the CPU overcommit ratio of a dedicated host does not affect the running status of the dedicated host. After a modification is complete, the number of allocated vCPUs on the dedicated host must not exceed the new total number of vCPUs. Otherwise, ECS instances that use the excess vCPUs cannot be started.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates a sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostAttribute&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyDedicatedHostAttribute|The operation that you want to perform. Set the value to ModifyDedicatedHostAttribute. |
|DedicatedHostId|String|Yes|dh-bp165p6xk2tlw61e\*\*\*\*|The ID of the dedicated host. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |
|DedicatedHostName|String|No|testDedicatedHostName|The name of the dedicated host. The name must be 2 to 128 characters in length and can contain letters, digits, colons \(:\), underscores \(\_\), and hyphens \(-\). It must start with a letter and cannot start with http:// or https://. |
|Description|String|No|testDescription|The description of the dedicated host. The description must be 2 to 256 characters in length and cannot start with http:// or https://. |
|ActionOnMaintenance|String|No|Migrate|The policy used to migrate the instances deployed on the dedicated host when the dedicated host fails or needs to be repaired online. Valid values:

-   Migrate: The instances are migrated to another physical server and restarted.
-   Stop: The instances are stopped. If the dedicated host cannot be repaired, the instances are migrated to another physical server and restarted.

If the dedicated host is attached with cloud disks, the default value is Migrate.

If the dedicated host is attached with local disks, the default value is Stop. |
|NetworkAttributes.SlbUdpTimeout|Integer|No|60|The timeout period for the UDP session between Server Load Balancer \(SLB\) and the dedicated host. Unit: seconds. Valid values: 15 to 310. |
|NetworkAttributes.UdpTimeout|Integer|No|60|The timeout period for the UDP session between a user and an Alibaba Cloud service on the dedicated host. Unit: seconds. Valid values: 15 to 310. |
|AutoPlacement|String|No|on|Specifies whether to add the dedicated host to the resource pool for automatic deployment. If you do not specify the **DedicatedHostId** parameter when you create an instance on a dedicated host, Alibaba Cloud automatically selects a dedicated host from the resource pool to host the instance. Valid values:

-   on: adds the dedicated host to the resource pool for automatic deployment.
-   off: does not add the dedicated host to the resource pool for automatic deployment.

For information about automatic deployment, see [Features](~~118938~~). |
|DedicatedHostClusterId|String|No|dc-bp165p6xk2tlw61e\*\*\*\*|The ID of the dedicated host cluster to which the dedicated host belongs. |
|CpuOverCommitRatio|Float|No|1|The CPU overcommit ratio. You can configure CPU overcommit ratios only for the following dedicated host types: g6s, c6s, and r6s. Valid values: 1 to 5.

The CPU overcommit ratio affects the number of available vCPUs on a dedicated host. You can use the following formula to calculate the number of available vCPUs on a dedicated host: Number of available vCPUs = Number of physical CPU cores × 2 × CPU overcommit ratio. For example, the number of physical CPU cores on each g6s dedicated host is 52. If you change the CPU overcommit ratio of a g6s dedicated host to 4, the number of available vCPUs on the dedicated host is 416. For scenarios that have minimal requirements for CPU stability or where CPU load is not heavy, such as development and test environments, you can increase the number of available vCPUs on a dedicated host by increasing the CPU overcommit ratio. This way, you can deploy more ECS instances of the same specifications on the dedicated host and reduce the unit deployment cost. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|2A4EA075-CB5B-41B7-B0EB-70D339F64DE7|The ID of the request. |

## Examples

Sample requests

```
http(s)://ecs.aliyuncs.com/? Action=ModifyDedicatedHostAttribute
&DedicatedHostId=dh-bp165p6xk2tlw61e****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyDedicatedHostAttributeResponse>
    <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</ModifyDedicatedHostAttributeResponse>
```

`JSON` format

```
{
    "RequestId":"2A4EA075-CB5B-41B7-B0EB-70D339F64DE7"
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|404|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|The error message returned because the specified DedicatedHostId parameter does not exist.|
|400|InvalidDedicatedHostName.Malformed|The specified parameter DedicatedHostName is not valid.|The error message returned because the specified DedicatedHostName parameter is invalid.|
|400|InvalidDescription.Malformed|The specified parameter Description is not valid.|The error message returned because the specified Description parameter is invalid. The description must be 2 to 256 characters in length and cannot start with http:// or https://.|
|403|InvalidUser.Unauthorized|The user is not authorized|The error message returned because you are not authorized to perform this operation.|
|400|InvalidParameter.SlbUdpTimeout|The specified value is invalid.|The error message returned because the specified NetworkAttributes.SlbUdpTimeout parameter is invalid.|
|400|InvalidParameter.UdpTimeout|The specified value is invalid.|The error message returned because the specified NetworkAttributes.UdpTimeout parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

