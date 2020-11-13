# RenewDedicatedHosts

You can call this operation to renew one or more subscription dedicated hosts.

## Description

By default, deductible vouchers are used first when you renew subscription dedicated hosts. You must make sure that your account supports the credit payment method.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=RenewDedicatedHosts&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|RenewDedicatedHosts|The operation that you want to perform. Set the value to RenewDedicatedHosts. |
|DedicatedHostIds|String|Yes|dh-bp199lyny9b3\*\*\*\*|The IDs of dedicated hosts. You can specify the IDs of up to 100 subscription dedicated hosts. Specify the dedicated host IDs in a JSON array. Example: `["dh-xxxxxxxxx", "dh-yyyyyyyyy", … "dh-zzzzzzzzz"]`. Separate the IDs with commas \(,\). |
|Period|Integer|Yes|1|The renewal period of the subscription dedicated host. For information about valid values, see the description of the `PeriodUnit` parameter. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. You can call the [DescribeRegions](~~25609~~) operation to query the most recent region list. |
|PeriodUnit|String|No|Month|The unit of the billing cycle. Default value: Month. Valid values:

-   Week: When the PeriodUnit parameter is set to Week, valid values of the `Period` parameter are 1, 2, 3, and 4.
-   Month: When the PeriodUnit parameter is set to Month, valid values of the `Period` parameter are 1, 2, 3, 4, 5, 6, 7, 8, 9, 12, 24, 36, 48, and 60. |
|ClientToken|String|No|123e4567-e89b-12d3-a456-426655440000|The client token that is used to ensure the idempotence of the request. You can use the client to generate the value, but you must make sure that the value is unique among different requests. The token can contain only ASCII characters and cannot exceed 64 characters in length. For more information, see [How to ensure idempotence](~~25693~~). |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|2A4EA075-CB5B-41B7-B0EB-70D339F64DE7|The ID of the request. |

## Examples

Sample requests

```
http(s)://ecs.aliyuncs.com/? Action=RenewDedicatedHosts
&DedicatedHostIds=dh-bp199lyny9b3****
&Period=1
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<RenewDedicatedHostsResponse>
    <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</RenewDedicatedHostsResponse>
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
|400|IdempotenceParamNotMatch|Request uses a client token in a previous request but is not identical to that request.|The error message returned because the specified client token in this request is not identical to the one used in the previous request.|
|400|InvalidClientToken.ValueNotSupported|The ClientToken provided is invalid.|The error message returned because the specified ClientToken parameter is invalid.|
|403|ChargeTypeViolation|Pay-As-You-Go dedicated host do not support this operation.|The error message returned because pay-as-you-go dedicated hosts do not support the current operation.|
|403|IncorrectHostStatus|The current status of the resource does not support this operation.|The error message returned because the operation is not supported while the resource is in the current state.|
|400|InvalidPeriod|The specified period is not valid.|The error message returned because the specified Period parameter is invalid.|
|403|LastTokenProcessing|The last token request is processing.|The error message returned because the previous token request is being processed. Try again later.|
|400|InvalidPeriodUnit.ValueNotSupported|The specified parameter PeriodUnit is not valid.|The error message returned because the specified PeriodUnit parameter is invalid.|
|400|InvalidDedicatedHostId.NotFound|The specified DedicatedHostId does not exist.|The error message returned because the specified dedicated host does not exist.|
|400|InvalidStatus.Upgrading|The dedicated host is upgrading, please try it later.|The error message returned because the specified dedicated host is being upgraded. Try again later.|
|500|InternalError|The request processing has failed due to some unknown error.|The error message returned because an internal error has occurred. Try again later. If the problem persists, submit a ticket.|
|400|LastOrderProcessing|The previous order is still processing, please try again later.|The error message returned because the previous order is being processed. Try again later.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

