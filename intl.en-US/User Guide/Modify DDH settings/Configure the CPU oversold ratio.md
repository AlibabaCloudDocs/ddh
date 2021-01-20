# Configure the CPU oversold ratio

Some dedicated host types allow you to configure the CPU oversold ratio. In scenarios that require lower CPU stability or where CPU load is not heavy, you can increase the CPU oversold ratio of a dedicated host. This way, you can increase the number of available vCPUs on the dedicated host. You can also deploy more ECS instances of the same specifications on the dedicated host and reduce the unit deployment cost.

-   The instance type of the dedicated host can be customized. These instance types include g6s, c6s, and r6s. For more information, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).
-   All the ECS instances on the dedicated host are in the **Stopped** state.

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  Select the dedicated host for which you want to configure the CPU oversold ratio. In the upper-left corner of the Dedicated Host tab, choose ![dropdown-menu](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4114511161/p199068.png)\>**Modify DDH Info**.

    ![modify-ratio](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7925690161/p201716.png)

5.  In the **Modify DDH Information** dialog box, specify the CPU oversold ratio.

    Valid values of Custom CPU Oversold Ratio: 1 to 5. Number of available vCPUs of a dedicated host = Number of CPU cores × 2 × CPU oversold ratio. For example, the number of CPU cores on each g6s dedicated host is 52. If you set the CPU oversold ratio of a g6s dedicated host to 4, the number of available vCPUs on the dedicated host is 416.

    ![input-ratio](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7925690161/p201718.png)

6.  Click **OK**.


**Related topics**  


[ModifyDedicatedHostAttribute](/intl.en-US/API Reference/Dedicated hosts/ModifyDedicatedHostAttribute.md)

