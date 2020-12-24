# Lifecycle of dedicated hosts

The lifecycle of a dedicated host \(DDH\) starts when it is created and ends when it is released. The status of the dedicated host changes during the lifecycle. This topic describes the statuses of a dedicated host.

The following table lists the statuses of a dedicated host.

|Status|Attribute|Description|Visible in the console|
|:-----|:--------|:----------|:---------------------|
|**Starting**|Transitory|After a dedicated host is created, the dedicated host is in the Starting state before its status changes to **Running**. If the dedicated host stays in the Starting state for a long time, it means that an error has occurred.|Yes|
|**Running**|Stable|The dedicated host is running. You can create and manage Elastic Compute Service \(ECS\) instances on the dedicated host.|Yes|
|**Physical Machine Risk**|Stable|The dedicated host is available. However, the dedicated host has potential risks and the ECS instances on the dedicated host may fail. You can migrate the dedicated host to another dedicated host. For more information, see [Migrate a dedicated host with hidden failures](/intl.en-US/User Guide/O&M of dedicated hosts/Migrate a dedicated host with hidden failures.md).|Yes|
|**Error**|Stable|An error has occurred on the dedicated host. You can [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to report and resolve the error.

|Yes|
|**Expired**|Stable|When a subscription dedicated host expires, it is in the Expired state. After you renew the dedicated host, its status changes from Expired to **Running**. For more information, see [Manual renewal of a dedicated host](/intl.en-US/User Guide/Renew a dedicated host/Manual renewal of a dedicated host.md).

|Yes|
|**Released**|Stable|If a subscription dedicated host is released due to expiration, its status changes to Released. All the resources of the dedicated host become unavailable. For more information, see [Subscription](/intl.en-US/Pricing/Subscription.md).|No|

