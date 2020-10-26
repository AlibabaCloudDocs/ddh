# ModifyDedicatedHostAutoReleaseTime

You can call this operation to set the automatic release time of a pay-as-you-go dedicated host or cancel the automatic release of a pay-as-you-go dedicated host.

## Description

When the specified time for automatic release is reached, the pay-as-you-go dedicated host will be automatically released. Make sure that you no longer use the host and have backed up all necessary application data.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostAutoReleaseTime&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyDedicatedHostAutoReleaseTime|The operation that you want to perform. Set the value to ModifyDedicatedHostAutoReleaseTime. |
|DedicatedHostId|String|Yes|dh-bp165p6xk2tlw61e\*\*\*\*|The ID of the dedicated host that you want to automatically release. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |
|AutoReleaseTime|String|No|2019-06-04T13:35:00Z|The automatic release time of the dedicated host. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC+0.

 -   The scheduled release time must be at least 30 mins from the current time.
-   The scheduled release time must be at most 3 years from the current time.
-   If the value of the seconds \(ss\) is not 00, it is automatically set to 00.
-   If you do not specify the `AutoReleaseTime` parameter, the automatic release is disabled. The dedicated host will not be released when the scheduled time is reached. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|04F0F334-1335-436C-A1D7-6C044FE73368|The ID of the request. |

## Examples

Sample requests

```
http(s)://ecs.aliyuncs.com/? Action=ModifyDedicatedHostAutoReleaseTime
&DedicatedHostId=dh-bp165p6xk2tlw61e****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyDedicatedHostAutoReleaseTimeResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
</ModifyDedicatedHostAutoReleaseTimeResponse>
```

`JSON` format

```
{
	"RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
}
```

## Error codes

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|MissingParameter|DedicatedHostId should not be null.|The error message returned because the DedicatedHostId parameter is not specified.|
|400|InvalidAutoReleaseTime.Malformed|The specified paramter autoReleaseTime is not valid.|The error message returned because the specified AutoReleaseTime parameter is invalid. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.|
|500|InternalError|The request processing has failed due to some unknown error, exception or failure.|The error message returned because an internal error has occurred. Try again later. If the problem persists, submit a ticket.|
|400|UnsupportedParameter|The parameters is unsupported.|The error message returned because the specified parameter is invalid.|
|403|ChargeTypeViolation|The operation is not permitted due to charge type of the dedicated host.|The error message returned because the billing method of the dedicated host does not support the operation.|
|404|NoSuchResource|The specified resource is not found.|The error message returned because the specified resource does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

