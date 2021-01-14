# Migrate ECS instances from a shared host to a dedicated host

You can migrate Elastic Compute Service \(ECS\) instances on a shared host to a dedicated host to address your workload requirements.

-   The ECS instance to be migrated must be in the **Stopped** state. For more information about how to stop an instance, see [Stop a subscription instance](/intl.en-US/Instance/Manage instances/Start ECS instances.md) or [Stop a pay-as-you-go instance](/intl.en-US/Instance/Manage instances/Start ECS instances.md).

    **Note:** Stopping an instance interrupts your workloads. Proceed with caution.

-   You have at least one dedicated host, and the dedicated host must meet the following requirements:
    -   The host and the migrating ECS instance belong to the same account, region, and zone.
    -   The host has sufficient resources for the migrating ECS instances. For more information about viewing the available resources of a dedicated host, see [View the resources of a dedicated host](/intl.en-US/User Guide/Auto-renewal of a dedicated host/View the resources of a dedicated host.md).
    -   The host supports the instance type of the migrating ECS instance. For more information about the instance types that are supported by dedicated hosts, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md). For more information about how to create a dedicated host, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

        **Note:** ECS instances attached with local disks cannot be migrated to a dedicated host attached with local SSDs.


Before you migrate an ECS instance, read the following:

-   When you migrate an ECS instance from a shared host to a dedicated host, the billing method of the ECS instance must be pay-as-you-go. You cannot migrate subscription instances or preemptible instances. You must convert subscription instances to pay-as-you-go instances before you can migrate them. For more information, see [Change the billing method of an instance from subscription to pay-as-you-go](/intl.en-US/Pricing/Change the billing method/Change the billing method of an instance from subscription to pay-as-you-go.md).
-   Pay-as-you-go ECS instances can be migrated to subscription dedicated hosts.

1.  Add the **Dedicated Host** column to the instance list.

    1.  In the upper-right corner of the Instances page, click the ![Customize column filters](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5653909951/p1350.png) icon.

    2.  In the Custom Filters dialog box, select **Dedicated Host** and click **OK**.

    The Dedicated Host column appears on the **Instances** page. You can check the column to see whether the ECS instance belongs to a dedicated host.

2.  Select the ECS instance to be migrated. In the **Operations** column, choose **More** \> **Instance Settings** \> **Modify DDH Deployment**.

3.  In the Modify DDH Deployment dialog box, complete the configurations by referring to the following table.

    |Parameter|Required|Description|
    |:--------|:-------|:----------|
    |**Target DDH**|Yes|Select the dedicated host to which the ECS instance is migrated. **Note:** If the **Target DDH** list is empty, it indicates that none of the dedicated hosts in your account meet the requirements to host the instance. For more information about dedicated host requirements, see [Requirements](#li_targetddh). |
    |**Associate with DDH**|No|Select whether to associate the instance with the target dedicated host. For more information, see [Associate with a dedicated host](/intl.en-US/Product Introduction/Features/Features.md).     -   **Yes**: The ECS instance is associated with the target dedicated host. After the instance is stopped with its computing resources released, the instance is still deployed on the dedicated host after it is restarted. If the available resources of the dedicated host are insufficient, the instance fails to be restarted.
    -   **No**: The ECS instance is not associated with the target dedicated host. After the instance is stopped with its computing resources released, the instance is still deployed on the dedicated host when it is restarted if the dedicated host has sufficient resources. If the available resources of the dedicated host are insufficient, the system automatically selects a dedicated host from the pool of dedicated hosts that allow automatic deployment.
 The default value is **No**. |

4.  Click **OK**.


Refresh the Instances page, and the corresponding value in the **Dedicated Host** column is updated. The instance is automatically started and enters the **Running** state.

