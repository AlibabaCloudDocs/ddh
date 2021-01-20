# View the host where an ECS instance resides

ECS instances can run on dedicated hosts or shared hosts. ECS instances can be migrated between a dedicated host and a shared host, or between two dedicated hosts. This topic describes how to view the host where an ECS instance resides.

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the top navigation bar, select a region.

3.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

4.  In the upper-right corner of the page, click ![display-config](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3493023061/p171315.png).

    ![config-icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6825690161/p201601.png)

5.  In the **Custom Filters** dialog box, select **Dedicated Host** and click **OK**.

6.  In the **Dedicated Host** column, view the host where the ECS instance resides.

    -   If the ID and name of a dedicated host are displayed, the ECS instance is running on the dedicated host.
    -   If **-** is displayed, the ECS instance is running on a shared host.
    ![display-ddh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6825690161/p201603.png)


**Related topics**  


[DescribeInstances](/intl.en-US/API Reference/Instances/DescribeInstances.md)

[Migrate ECS instances between different dedicated hosts](/intl.en-US/User Guide/Migrate ECS instances/Migrate ECS instances between different dedicated hosts.md)

[Migrate an ECS instance from a shared host to a dedicated host](/intl.en-US/User Guide/Migrate ECS instances/Migrate ECS instances from a shared host to a dedicated host.md)

[Migrate an ECS instance from a dedicated host to a shared host](/intl.en-US/User Guide/Migrate ECS instances/Migrate an ECS instance from a dedicated host to a shared host.md)

