# Migrate ECS instances between different dedicated hosts

You can migrate Elastic Compute Service \(ECS\) instances between different dedicated hosts that belong to your account to address your workload requirements.

-   The ECS instance to be migrated must be in the **Stopped** state. For more information about how to stop an instance, see [Stop an instance](/intl.en-US/Instance/Manage instances/Stop an instance.md).

    **Note:** Stopping an instance interrupts your workloads. Proceed with caution.

-   The ECS instance to be migrated must be in the **Stopped** state. For more information about how to stop an instance, see [Stop a subscription instance](/intl.en-US/Instance/Manage instances/Start ECS instances.md) or [Stop a pay-as-you-go instance](/intl.en-US/Instance/Manage instances/Start ECS instances.md).

    **Note:** Stopping an instance interrupts your workloads. Proceed with caution.

-   The target dedicated host must meet the following conditions:
    -   The host and the migrating ECS instance belong to the same account, region, and zone.
    -   The host has sufficient resources for the migrating ECS instance. For more information about how to view the available resources of a dedicated host, see [View the resources of a dedicated host](/intl.en-US/User Guide/Auto-renewal of a dedicated host/View the resources of a dedicated host.md).
    -   The host supports the instance type of the migrating ECS instance. For more information about the instance types that are supported by dedicated hosts, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md). For more information about how to create a dedicated host, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

        **Note:** ECS instances attached with local disks cannot be migrated to a dedicated host attached with local SSDs.

    -   The host matches the billing method of the migrating ECS instance.

        You can run subscription ECS instances or pay-as-you-go ECS instances on subscription dedicated hosts. If the migrating ECS instance is a subscription instance, the expiration time of the instance must not end later than the expiration time of the target dedicated host.


1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  Log on to the [ECS console](https://partners-intl.console.aliyun.com/#/ecs).

3.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

4.  In the top navigation bar, select a region.

5.  On the Instances page, add the **Dedicated Host** column.

    1.  In the upper-right corner of the Instances page, click the ![Configuration](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5653909951/p1350.png) icon.

    2.  In the Custom Filters dialog box, select **Dedicated Host** and click **OK**.

    The Dedicated Host column appears on the **Instances** page. You can view the column to check whether the ECS instance belongs to a dedicated host.

6.  Select the migrating ECS instance. In the **Operations** column, choose **More** \> **Instance Settings** \> **Modify DDH Deployment**.

7.  In the Modify DDH Deployment dialog box, complete the configurations by referring to the following table.

    |Parameter|Required|Description|
    |:--------|:-------|:----------|
    |**Target DDH**|Yes|Select the dedicated host to which the ECS instance is migrated. **Note:** If none of the dedicated hosts in your account meet the requirements to host the instance, then the **Target DDH** list is empty. For more information about dedicated host requirements, see [Prerequisites](#li_targetddh). |
    |**Associate with DDH**|No|Select whether to associate the instance with the target dedicated host. For more information about how to associate an instance with a host, see [Host association](/intl.en-US/Product Introduction/Features.md).     -   **Yes**: The ECS instance is associated with the target dedicated host. After the instance is stopped with its computing resources released, the instance is still deployed on the dedicated host when the instance is restarted. If the available resources of the dedicated host are insufficient, the instance fails to be restarted.
    -   **No**: The ECS instance is not associated with the target dedicated host. After the instance is stopped with its computing resources released, the instance is still deployed on the dedicated host when it is restarted if the dedicated host has sufficient resources. If the available resources of the dedicated host are insufficient, the system automatically selects a dedicated host from the pool of dedicated hosts that allow automatic deployment. |

8.  Click **OK**.


Refresh the Instances page, and the corresponding value in the **Dedicated Host** column is updated. The instance is automatically started, and then the status of the instance enters **Running**.

