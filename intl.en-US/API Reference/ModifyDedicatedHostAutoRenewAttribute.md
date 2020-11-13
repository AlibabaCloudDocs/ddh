# ModifyDedicatedHostAutoRenewAttribute

You can call this operation to enable or disable auto-renewal for one or more subscription dedicated hosts.

## Description

Subscription dedicated hosts are automatically renewed nine days before expiration. The automatic payment is deducted at 08:00:00 \(UTC+8\). If the automatic payment fails, the payment is deducted at the same time the next day. Automatic payment stops after the payment succeeds or after the dedicated host is expired and locked. Make sure that your account has sufficient balance or credit for the payment.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Ecs&api=ModifyDedicatedHostAutoRenewAttribute&type=RPC&version=2014-05-26)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyDedicatedHostAutoRenewAttribute|The operation that you want to perform. Set the value to ModifyDedicatedHostAutoRenewAttribute. |
|DedicatedHostIds|String|Yes|dh-bp165p6xk2tlw61e\*\*\*\*|The IDs of the dedicated hosts. You can enter up to 100 subscription dedicated host IDs in the list. Separate multiple IDs with commas \(,\). |
|RegionId|String|Yes|cn-hangzhou|The region ID of the dedicated host. |
|Duration|Integer|No|1|The renewal period of the subscription dedicated host. For information about the valid values, see the description of the `PeriodUnit` parameter. |
|PeriodUnit|String|No|Month|The unit of the renewal period. Default value: Month. Valid values:

-   Week: When the PeriodUnit parameter is set to Week, valid values of the `Duration` parameter are 1, 2, and 3.
-   Month: When the PeriodUnit parameter is set to Month, valid values of the `Duration` parameter are 1, 2, 3, 6, and 12. |
|AutoRenew|Boolean|No|false|Specifies whether to automatically renew the subscription dedicated host. Default value: false. Valid values:

-   true: The subscription dedicated host is automatically renewed.
-   false: The subscription dedicated host is not automatically renewed. |
|RenewalStatus|String|No|Normal|Specifies whether to enable auto-renewal for the subscription dedicated host. The `RenewalStatus` parameter takes precedence over the `AutoRenew` parameter. Valid values:

-   AutoRenewal: The dedicated host is automatically renewed.
-   Normal: The dedicated host is not automatically renewed but you still receive notifications for renewals.
-   NotRenewal: Auto-renewal is disabled and no expiration notification is sent. You receive notifications for renewal three days before the expiration time of the subscription dedicated host. You can change the value of this parameter from NotRenewal to Normal for a dedicated host and manually renew it by calling the [RenewDedicatedHosts](~~134250~~) operation. Alternatively, you can renew it by setting this parameter to AutoRenewal. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|2A4EA075-CB5B-41B7-B0EB-70D339F64DE7|The ID of the request. |

## Examples

Sample requests

```
http(s)://ecs.aliyuncs.com/? Action=ModifyDedicatedHostAutoRenewAttribute
&DedicatedHostIds=dh-bp165p6xk2tlw61e****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyDedicatedHostAutoRenewAttributeResponse>
    <RequestId>2A4EA075-CB5B-41B7-B0EB-70D339F64DE7</RequestId>
</ModifyDedicatedHostAutoRenewAttributeResponse>
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
|403|MissingParameter.DedicatedHostId|DedicatedHostId should not be null.|The error message returned because the DedicatedHostIds parameter is not specified.|
|403|InvalidParameter.ToManyDedicatedHostIds|DedicatedHostId should be less than 100.|The error message returned because more than 100 dedicated host IDs are specified in the DedicatedHostIds parameter.|
|403|InvalidParameter.InvalidDedicatedHostId|%s|The error message returned because the specified DedicatedHostIds parameter is invalid.|
|403|IncorrectHostStatus|The current status of the resource does not support this operation.|The error message returned because the operation is not supported while the resource is in the current state.|
|403|ChargeTypeViolation|Pay-As-You-Go dedicated host do not support this operation.|The error message returned because the current operation is not supported for pay-as-you-go dedicated hosts.|
|403|InvalidParameter.Duration|%s|The error message returned because the specified Duration parameter is invalid.|
|403|InvalidParameter.RenewalStatus|%s|The error message returned because the specified RenewalStatus parameter is invalid.|
|403|InvalidPeriodUnit.ValueNotSupported|The specified parameter PeriodUnit is not valid.|The error message returned because the specified PeriodUnit parameter is invalid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs).

