# Limits

This topic describes the limits that apply when you use dedicated hosts.

The following table describes the limits that apply when you use dedicated hosts. In addition, the limits on Elastic Compute Service \(ECS\) resources also apply to ECS instances that are created on dedicated hosts. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).

|Limit|Description|Exception|
|:----|:----------|:--------|
|Creation of dedicated hosts|Before you create dedicated hosts in mainland China, you must complete the [real-name verification](https://www.alibabacloud.com/help/doc-detail/52595.htm).

|None|
|Supported network types|Virtual private cloud \(VPC\) is supported. For more information, see [What is a VPC?](/intl.en-US/Product Introduction/What is a VPC?.md)|None|
|Billing methods of dedicated hosts and ECS instances|You can create pay-as-you-go or subscription ECS instances on subscription dedicated hosts.

|None|
|Creation of subscription ECS instances on a subscription dedicated host

|The expiration date of subscription ECS instances cannot be later than that of the dedicated host.|None|
|Renewal of subscription ECS instances on a subscription dedicated host

|The expiration date of subscription ECS instances cannot be later than that of the dedicated host. If the auto-renewal period of subscription ECS instances do not meet this requirement, the auto-renewal fails.|None|
|Switch of the billing method of ECS instances on a dedicated host from pay-as-you-go to subscription|The expiration date of subscription ECS instances cannot be later than that of the dedicated host.

|None|
|Change of the billing method of dedicated hosts|None.|None|
|Migration of ECS instances between a shared host and a dedicated host|Only pay-as-you-go ECS instances can be migrated. Both subscription ECS instances and preemptible instances cannot be migrated.

|None|
|Migration of ECS instances between different dedicated hosts|You can migrate ECS instances only between the same type of dedicated hosts. The dedicated hosts must belong to the same Alibaba Cloud account. ECS instances that run on local SSD hosts cannot be migrated. For more information about dedicated host types, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).|None|

