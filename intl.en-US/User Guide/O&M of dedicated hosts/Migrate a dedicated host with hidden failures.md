# Migrate a dedicated host with hidden failures

If a dedicated host has potential risks, it is still available. However, the dedicated host and the Elastic Compute Service \(ECS\) instances on it may fail at any time. To protect your business against risks that result in possible failures of the dedicated host, we recommend you migrate the dedicated host to another dedicated host.

All the ECS instances on the dedicated host are stopped.

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  On the Dedicated Hosts page, find the dedicated host. In the **Status** column, move the pointer over **Physical Machine Risk**. In the **Note** message, click **Change Host**.

    ![Change the dedicated host](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0753909951/p135221.png)

5.  Perform operations based on the dedicated host type.

    -   If the dedicated host is not a local SSD host, click **OK**.
    -   If the dedicated host is a local SSD host, click **Submit Ticket**.

        **Note:** ECS instances that run on local SSD hosts cannot be automatically migrated. You must submit a ticket to manually migrate the data of the dedicated host. However, the data on the local disk is lost after the manual migration.

    After all the ECS instances on the dedicated host are migrated to another dedicated host, the host ID and the metadata of the ECS instances remain unchanged. The metadata includes the ID, private IP address, and public IP address of each ECS instance. However, the machine ID of the dedicated host is changed.


