# Resource billing for ECS instances on a dedicated host

This topic describes how you are billed for Elastic Compute Service \(ECS\) resources when you deploy ECS instances on a dedicated host.

For ECS instances that run on a dedicated host, you are not charged for the vCPUs, memory resources, and local SSDs of the instances. However, you are charged for the images, disks, public bandwidth, and snapshots of the ECS instances. For more information, see [Subscription](/intl.en-US/Pricing/Billing methods/Subscription.md), [Public bandwidth](/intl.en-US/Pricing/Billing items/Public bandwidth.md), [Snapshots](/intl.en-US/Pricing/Billing items/Snapshots.md), and [EIP billing](/intl.en-US/Pricing/Billing.md).

If a subscription dedicated host is running, the billing of the resources associated with the ECS instances on the dedicated host varies with the resource statuses.

## Running ECS instances

All ECS instances that are in the **Running** state incur fees regardless of their billing methods.

## Stopped ECS instances

Stopped ECS instances still incur fees. The billing of the associated resources varies with the billing methods of the instances.

-   Subscription ECS instances

    After a subscription ECS instance is stopped, you are still charged for all billable resources.

-   Pay-as-you-go ECS instances

    Compared with the pay-as-you-go ECS instances on a shared host, the pay-as-you-go ECS instances on a dedicated host does not support the No Fees for Stopped Instances feature. After a pay-as-you-go ECS instance is stopped, the billing of its associated resources has the following changes:

    -   Image: Images are retained. The billing of paid images continues.
    -   Public bandwidth:
        -   If the instance is assigned a public IP address, the IP address is released and you are no longer charged for the public bandwidth.
        -   If the instance is attached to an elastic IP address \(EIP\), the EIP remains unchanged and the billing continues.

            **Note:** After the instance is stopped, the private IP address remains unchanged.

    -   Disks are retained and you are still charged for them.
    -   Snapshots are retained and you are still charged for them.

If you create a pay-as-you-go ECS instance, you can reduce costs by using the following methods:

-   [Reserved instances](/intl.en-US/Pricing/Billing methods/Reserved instances.md)
-   [Storage capacity units](/intl.en-US/Pricing/Billing methods/Storage capacity units.md)
-   [Savings plans](/intl.en-US/Pricing/Billing methods/Savings plans.md)

**Note:** We recommend that you create pay-as-you-go ECS instances on a dedicated host to improve resource elasticity.

