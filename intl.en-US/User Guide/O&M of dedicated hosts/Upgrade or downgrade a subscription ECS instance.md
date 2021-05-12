# Upgrade or downgrade a subscription ECS instance

This topic describes how to upgrade or downgrade a subscription ECS instance. If an Elastic Compute Service \(ECS\) instance that is created on a dedicated host is no longer suited to your business requirements, you can upgrade or downgrade the instance specifications. For example, you can upgrade or downgrade the number of vCPUs and the memory size of instance types. You can also upgrade or downgrade the public bandwidth of the ECS instance.

Only Virtual private cloud \(VPC\) is supported. Therefore, all ECS instances described in this topic are VPC-connected ECS instances.

## Upgrade or downgrade the instance type

If you want to upgrade or downgrade a predefined instance type, you can select only the predefined specifications. However, if you want to upgrade or downgrade a custom instance type, you can modify the number of vCPUs or the memory size. The following table describes the methods that you can use to upgrade or downgrade the instance type.

|Operation|Method|Notes|Reference|
|:--------|------|-----|---------|
|Upgrade|Use the specification upgrade feature.Before you upgrade the instance type, make sure that the ECS instance is in the **Stopped** state.

|The new instance type immediately takes effect after the ECS instance is restarted.|[Upgrade the instance types of subscription instances](/intl.en-US/Instance/Change configurations/Change instance types/Upgrade the instance types of subscription instances.md)|
|Downgrade|Use the configuration downgrade feature.Before you downgrade the instance type, make sure that the ECS instance is in the **Stopped** state.

|The new instance type immediately takes effect after the ECS instance is restarted.|[Downgrade the instance types of subscription instances](/intl.en-US/Instance/Change configurations/Change instance types/Downgrade the instance types of subscription instances.md)|
|Use the renewal and configuration downgrade feature. This feature allows you to downgrade the predefined instance type when you renew your ECS instances.**Note:** You cannot use this feature to downgrade a custom instance type.

|The new instance type takes effect in the next billing cycle. If you use this method, you must use the DDH console or API operations to restart the instance within the first seven days of the new billing cycle.|-   [Downgrade the configurations of an instance during renewal](/intl.en-US/Pricing/Renew instances/Downgrade the configurations of an instance during renewal.md)
-   [Reboot the instance](/intl.en-US/Instance/Manage instances/Restart an instance.md)
-   [RebootInstance](/intl.en-US/API Reference/Instances/RebootInstance.md) |

## Upgrade or downgrade the public bandwidth

The following table describes the methods that you can use to upgrade or downgrade the public bandwidth.

**Note:** You can upgrade or downgrade only the public bandwidth of the subscription ECS instances that are not associated with an elastic IP address \(EIP\). For more information, see [Modify the bandwidth of an EIP](/intl.en-US/Instance/Change configurations/Modify bandwidth configurations/Modify the bandwidth of an EIP.md).

|Operation|Method|Notes|Reference|
|---------|------|-----|---------|
|Upgrade|Use the configuration upgrade feature.|The upgraded public bandwidth immediately takes effect.**Note:** If you upgrade the public bandwidth of an ECS instance from 0 Mbit/s to a higher value, a public IP address is automatically allocated to the ECS instance.

|[Modify the bandwidth configurations of subscription instances](/intl.en-US/Instance/Change configurations/Modify bandwidth configurations/Modify the bandwidth configurations of subscription instances.md)|
|Downgrade|Use the configuration downgrade feature.|The downgraded public bandwidth immediately takes effect.**Note:** If you downgrade the public bandwidth of an ECS instance to 0, the public IP address is automatically detached.

|[Modify the bandwidth configurations of subscription instances](/intl.en-US/Instance/Change configurations/Modify bandwidth configurations/Modify the bandwidth configurations of subscription instances.md)|
|Use the renewal and configuration downgrade feature. This feature allows you to downgrade the public bandwidth when you renew your ECS instances.**Note:** You cannot use the feature to downgrade a custom instance type.

|The new public bandwidth takes effect in the next billing cycle.**Note:** If you downgrade the public bandwidth of an ECS instance to 0, the public IP address is automatically detached.

|[Downgrade the configurations of an instance during renewal](/intl.en-US/Pricing/Renew instances/Downgrade the configurations of an instance during renewal.md)|

