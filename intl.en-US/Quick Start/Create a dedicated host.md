# Create a dedicated host

This topic describes how to create a subscription dedicated host in the Elastic Compute Service \(ECS\) console.

-   An Alibaba Cloud account is created. For more information, see [Create an Alibaba Cloud account](https://www.alibabacloud.com/help/doc-detail/50482.htm).
-   A credit card or PayPal account is associated with your Alibaba Cloud account. For more information, see [Add a payment method](https://www.alibabacloud.com/help/doc-detail/50517.htm).

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  On the Dedicated Hosts page, click **Create DDH**.

5.  On the page that appears, set the following parameters:

    1.  **Billing Method**: Select **Subscription**.

    2.  **Region**: Select a region and a zone where you want to create a dedicated host.

        For example, to create a dedicated host in the China \(Beijing\) region, select **China \(Beijing\)** from the drop-down list. For more information, see [Regions and zones](https://www.alibabacloud.com/help/doc-detail/123712.htm).

    3.  **Dedicated Host Type**, **DDH Name**, and Quantity: Select a dedicated host type, enter a dedicated host name, and then specify the number of dedicated hosts that you want to purchase.

        The dedicated host type determines the instance family and the maximum number of ECS instances that you can deploy on the dedicated host. The host types g6s, c6s, and r6s allow you to customize the vCPU-to-memory ratio. This allows you to flexibly allocate computing resources when you create ECS instances. For more information about dedicated host types, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).

        **Note:** ECS instances on local SSD i2 dedicated hosts do not support manual migration and automatic failover. If a local SSD i2 dedicated host fails, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for manual migration. However, the data on local disks will be lost after the migration.

    4.  Add tags.

        You can assign tags to dedicated hosts and manage them in groups. For more information, see [Overview](/intl.en-US/Tag & Resource/Tags/Overview.md).

    5.  Select a resource group.

        You can separate dedicated hosts into different resource groups and set different access permissions for these dedicated hosts. For more information, see [Resource groups](/intl.en-US/Tag & Resource/Resource/Resource groups.md).

    6.  In the **DDH Settings** section, set the following parameters.

        |Parameter|Description|
        |:--------|-----------|
        |**Allow Automatic Deployment**|        -   If you select Allow Automatic Deployment, ECS instances are automatically deployed on available dedicated hosts. For more information, see [Automatic deployment](/intl.en-US/Product Introduction/Features.md).
        -   If you do not select Allow Automatic Deployment, you must specify a dedicated host when you create an ECS instance.
The Allow Automatic Deployment option is selected by default. |
        |**Automatic Instance Migration upon DDH Failure**|        -   If you select Automatic Instance Migration upon DDH Failure, ECS instances on a dedicated host are automatically migrated to another dedicated host if the original dedicated host fails.
        -   If you do not select this option, you must [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to apply for a new dedicated host if the original dedicated host fails.
The Automatic Instance Migration upon DDH Failure option is selected by default. You can modify this setting after the dedicated host is created. For more information, see [Modify the settings of automatic instance migration for a dedicated host](/intl.en-US/User Guide/Modify the settings of automatic instance migration for a dedicated host.md).

**Note:** This option is unavailable for local SSD i2 dedicated hosts. |
        |**CPU Oversold Ratio**|The CPU overcommit ratio affects the number of available vCPUs on a dedicated host. You can use the following formula to calculate the number of available vCPUs on a dedicated host: Number of available vCPUs = Number of physical CPU cores × 2 × CPU overcommit ratio. In scenarios where high CPU stability is not required, such as development and test environments, you can increase the number of available vCPUs on a dedicated host by increasing the CPU overcommit ratio. This way, you can deploy more ECS instances of the same specification on the dedicated host and reduce the unit deployment cost.**Note:** You can configure CPU overcommit ratios only for the following dedicated host types: g6s, c6s, and r6s.

For example, the number of physical CPU cores on each g6s dedicated host is 52. If you set the CPU overcommit ratio of a g6s dedicated host to 4, the number of available vCPUs on the dedicated host is 416. |

    7.  Set the **Duration** parameter and select the **Enable Auto-renewal** option based on your business requirements.

    8.  Read and agree to the **Dedicated Host Terms of Service**.

    9.  In the lower-right corner, confirm the cost next to **Total** and click **Preview**.

6.  In the **Preview** dialog box, confirm the configurations and click **Create Order**.

7.  On the page that appears, follow the instructions to complete the payment.


You can view the created dedicated host on the Dedicated Hosts page. If the dedicated host is in the **Running** state, you can use the dedicated host. If the created dedicated host does not appear on the Dedicated Hosts page, wait for a while and refresh the page.

You can perform the following operations:

-   [Create ECS instances on a dedicated host](/intl.en-US/Quick Start/Create ECS instances on a dedicated host.md)
-   [Migrate ECS instances from a shared host to a dedicated host](/intl.en-US/User Guide/Migrate ECS instances from a shared host to a dedicated host.md)

