# Associate an ECS instance with a dedicated host

You can stop an ECS instance and release the CPU and memory resources. If you want the instance to be still deployed on the original dedicated host when you restart the instance, you can associate the instance with the dedicated host. This topic describes how to associate an ECS instance with a dedicated host.

Make sure that you have created an ECS instance on a dedicated host. For more information, see [Create ECS instances on a dedicated host](/intl.en-US/Quick Start/Create ECS instances on a dedicated host.md).

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

3.  In the top navigation bar, select a region.

4.  Select the target ECS instance. In the **Actions** column, choose **More** \> **Instance Settings** \> **Modify DDH Deployment**.

5.  In the Modify DDH Deployment dialog box, from the **Associate with DDH** list, select **Yes**.

    Once the ECS instance is associated with the dedicated host, if the instance is stopped with its computing resources released, the restarted instance is still deployed on the dedicated host. If the available resources of the dedicated host are insufficient, the instance fails to be restarted. For more information about associating a host, see [Host association](/intl.en-US/Product Introduction/Features.md).

6.  Click **OK**.


In the **Associate with DDH** column of the instance, the value is changed to **Yes**. You can view the results by performing the following steps:

1.  In the left-side navigation pane, choose **Dedicated Hosts**.
2.  Select the dedicated host where the target ECS instance resides. In the **Operations** column, click **Details**.
3.  In the Instances list, select the target ECS instance and check the **Associate with DDH** column.

