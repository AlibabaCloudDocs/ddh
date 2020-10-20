# Migrate an ECS instance from a dedicated host to a shared host

You can migrate an Elastic Compute Service \(ECS\) instances from a dedicated host to a shared host to a dedicated host. This allows you to flexibly deploy your business.

The ECS instance to be migrated is in the **Stopped** state.

**Note:** Your business is interrupted if you stop the instance. Proceed with caution.

You must note the following limits:

-   Only pay-as-you-go instances can be migrated. To migrate subscription instances, you must convert them to pay-as-you-go instances. For more information, see [Change the billing method of instances from subscription to pay-as-you-go](/intl.en-US/Pricing/Change the billing method/Change the billing method of instances from subscription to pay-as-you-go.md).
-   Instances of the local SSD type cannot be migrated.

**Note:** After an ECS instance is migrated from a dedicated host to a shared host, you must pay for the vCPUs, memory, and local disks. The costs of these resources are no longer included in DDH bills. Ensure that your account has sufficient balance. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Billing methods/Pay-as-you-go.md).

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  Find the dedicated host. In the **Actions** column, click **Details**.

5.  Find the ECS instance to be migrated in the pane that appears. In the **Actions** column, click **Modify DDH Deployment**.

6.  Set the following parameters.

    |Parameter|Description|
    |:--------|:----------|
    |**Destination DDH**|Select **Shared Host**.|
    |**Target instance type**|Enter an instance type, such as ecs.g6.large. For more information about the features and metrics of each instance type, see [Instance families](/intl.en-US/Instance/Instance families.md).The following conditions must be met to ensure the success of the migration:

    -   The source instance type can be changed to the destination instance type. For more information, see [Change instance types of instances](/intl.en-US/Instance/Change configurations/Change instance types of instances.md).
    -   The destination instance type is available in the zone where the dedicated host resides. |

7.  Click **OK**.

    After the migration is complete, the ECS instance is automatically started. The instance is in the **Running** state after being started.

8.  You can view the host on which the ECS instance runs on the **Instances** page.

    1.  In the upper-right corner of the page, click ![display-config](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3493023061/p171315.png).

    2.  Select **Dedicated Host**, and then click **OK**.

    3.  Find the ECS instance, and view the host in the **Dedicated Host** column.

        The value **-** indicates that the ECS instance runs on a shared host.


