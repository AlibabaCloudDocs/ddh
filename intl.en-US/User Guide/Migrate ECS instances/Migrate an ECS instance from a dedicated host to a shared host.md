# Migrate an ECS instance from a dedicated host to a shared host

You can migrate an Elastic Compute Service \(ECS\) instance from a dedicated host to a shared host. This allows you to flexibly deploy your business.

The ECS instance that you want to migrate must meet the following requirements:

-   The ECS instance is stopped. For more information, see [Stop an instance](/intl.en-US/Instance/Manage instances/Stop an instance.md).

    **Note:** Your business is interrupted if you stop the instance. Proceed with caution.

-   The billing method is pay-as-you-go. To migrate subscription instances, you must first convert them to pay-as-you-go instances. For more information, see [Change the billing method of an instance from subscription to pay-as-you-go](/intl.en-US/Pricing/Change the billing method/Change the billing method of an instance from subscription to pay-as-you-go.md).
-   The dedicated host is not a local SSD host.

After you migrate an ECS instance from a dedicated host to a shared host, you are charged for the vCPUs, memory, and local disks. The costs of these resources are no longer included in DDH bills. Make sure that your account has sufficient balance. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Billing methods/Pay-as-you-go.md).

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  In the **Modify Host Deployment** dialog box, set the required parameters.

    |Parameter|Description|
    |:--------|:----------|
    |**Destination DDH**|Select **Shared Host**.|
    |**Target Instance Type**|Enter an instance type, for example, ecs.g6.large. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).The destination instance type must meet the following requirements. This ensures the success of the migration.

    -   The source instance type can be changed to the destination instance type. For more information, see [Instance families that support instance type changes](/intl.en-US/Instance/Change configurations/Instance families that support instance type changes.md).
    -   The destination instance type is available in the zone where the dedicated host resides. |

    ![2-sharedhost](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0725690161/p201840.png)

5.  Click **OK**.

    After the migration is complete, the ECS instance automatically starts and enters the **Running** state.


**Related topics**  


[ModifyInstanceDeployment](/intl.en-US/API Reference/Dedicated hosts/ModifyInstanceDeployment.md)

