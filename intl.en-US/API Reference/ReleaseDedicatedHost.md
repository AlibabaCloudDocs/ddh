# ReleaseDedicatedHost

You can call this operation to release a pay-as-you-go dedicated host.

## Description

Before you release a pay-as-you-go dedicated host, make sure that no ECS instances are deployed on the dedicated host.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=ReleaseDedicatedHost&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ReleaseDedicatedHost|The operation that you want to perform. Set the value to ReleaseDedicatedHost. |
|DedicatedHostId|String|Yes|dh-bp199lyny9b3\*\*\*\*|The ID of the dedicated host. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|A1B15AC8-E6F6-49A4-8985-8C07104B9199|The ID of the request. |

## Examples

Sample requests

```
http(s)://ecs.aliyuncs.com/?Action=ReleaseDedicatedHost
&DedicatedHostId=dh-bp199lyny9b3****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ReleaseDedicatedHostResponse>
    <RequestId>A1B15AC8-E6F6-49A4-8985-8C07104B9199</RequestId>
</ReleaseDedicatedHostResponse>
```

`JSON` format

```
{
    "RequestId":"A1B15AC8-E6F6-49A4-8985-8C07104B9199"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|InstanceExist|Instance exists on the dedicated host.|The error message returned because ECS instances exist on the dedicated host. You must remove the instances before you can release the dedicated host.|
|400|ChargeTypeViolation|The operation is not permitted due to charge type of the dedicated host.|The error message returned because the billing method of the dedicated host does not support the operation.|
|400|IncorrectHostStatus.Initializing|The specified dedicatedHost status is not support this operation|The error message returned because the operation is not supported while the dedicated host is in the current state.|
|404|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|The error message returned because the specified DedicatedHostId parameter does not exist.|
|500|InternalError|The request processing has failed due to some unknown error.|The error message returned because an internal error has occurred. Try again later. If the problem persists, submit a ticket.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

