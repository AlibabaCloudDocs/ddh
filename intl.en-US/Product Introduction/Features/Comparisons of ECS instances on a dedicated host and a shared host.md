# Comparisons of ECS instances on a dedicated host and a shared host

This topic describes the differences between the Elastic Compute Service \(ECS\) instances that run on a dedicated host and on a shared host.

The following table lists the differences.

|Item|ECS instances on a shared host|ECS instances on a dedicated host|
|:---|:-----------------------------|:--------------------------------|
|Network type|Virtual private clouds \(VPCs\) and the classic network are supported. For more information, see [Network types](/intl.en-US/Network/Network types.md).|Only VPCs are supported.|
|Billable item|See [Billing overview](/intl.en-US/Pricing/Billing overview.md).|See [Resource billing for ECS instances on a dedicated host](/intl.en-US/Pricing/Resource billing for ECS instances on a dedicated host.md).|
|Billing method|Subscription, pay-as-you-go, preemptible instances, and reserved instances are supported.

|Subscription and pay-as-you-go are supported. |
|Renewal|You can specify the renewal period based on your business requirements.|When you specify the renewal period, the expiration date of the instance cannot be later than that of the subscription dedicated host. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).|
|No fees for stopped instances|See [No Fees for Stopped Instances \(VPC-Connected\)](/intl.en-US/Pricing/Billing methods/No Fees for Stopped Instances (VPC-Connected).md).|After the no fees for stopped instances feature is enabled for an instance, the resources of the dedicated host are released when the instance is stopped. These resources include the vCPUs and memory. Resources are reallocated to the dedicated host when the instance is restarted. For more information, see [Subscription](/intl.en-US/Pricing/Subscription.md).|
|Switch the billing method from pay-as-you-go to subscription|Before you switch the billing method of an instance, the instance must meet the prerequisites. For more information, see [Change the billing method of an instance from pay-as-you-go to subscription](/intl.en-US/Pricing/Change the billing method/Change the billing method of an instance from pay-as-you-go to subscription.md).

|Before you switch the billing method of an instance, the instance must meet the prerequisites. The feature is applicable only to the instances on a pay-as-you-go dedicated host. After the billing method of an ECS instance is switched to subscription, the expiration date of the instance cannot be later than that of the dedicated host.|
|ECS instance type|See [Instance families](/intl.en-US/Instance/Instance families.md).|For information about ECS instance families that are supported by each type of dedicated host, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).|
|Create an ECS instance|See [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).|See [Create ECS instances on a dedicated host](/intl.en-US/Quick Start/Create ECS instances on a dedicated host.md).|
|Upgrade or downgrade an ECS instance|See [Change instance types](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).|See [t1836068.md\#](/intl.en-US/User Guide/O&M of dedicated hosts/Upgrade or downgrade a subscription ECS instance.md).|
|Adjust public bandwidth|See [Modify public bandwidth](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).|See [Modify public bandwidth](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).|
|Assign public IP addresses|See [Modify public bandwidth](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).|See [Modify public bandwidth](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).|
|Release an ECS instance|-   Pay-as-you-go ECS instances can be manually or automatically released. For more information, see [Release an instance](/intl.en-US/Instance/Manage instances/Release an instance.md).
-   If you do not renew a subscription ECS instance after it expires, the instance is automatically released. If the payment of a pay-as-you-go ECS instance is overdue and you do not add funds to the account that owns the ECS instance, the ECS instance is automatically released.

|If you do not renew a subscription dedicated host after it expires, the ECS instances on the dedicated host are automatically released.|

