# Modify the settings of automatic instance migration for a dedicated host

Alibaba Cloud allows you to migrate the instances deployed on a dedicated host if the dedicated host fails. The instance migration minimizes the impact of the failure on your business. This topic describes how to modify the settings of automatic instance migration for a dedicated host.

You can enable the automatic instance migration feature when or after you create a dedicated host.

-   If you want to enable the automatic instance migration feature when you create a dedicated host, log on to the Elastic Compute Service \(ECS\) console. In the left-side navigation pane, choose Instances & Images Dedicated Hosts. In the top navigation bar, select a region, and click Create DDH. On the page that appears, select **Automatic Instance Migration upon DDH Failure** in the **DDH Settings** section. For information about how to create a dedicated host, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).
-   For information about how to modify the configuration of automatic instance migration upon DDH failure, see [Modify the settings of automatic instance migration for a dedicated host](/intl.en-US/User Guide/Modify the settings of automatic instance migration for a dedicated host.md).

**Note:** You cannot perform manual migration of ECS instances on local SSD dedicated hosts such as Local SSD type i2 upon DDH failure. In addition, you cannot perform automatic migration of ECS instances on local SSD dedicated hosts. If local SSD dedicated hosts fail, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for a manual migration. However, the data in the local disk is lost after migration.

After the automatic instance migration feature is enabled for a dedicated host, the ECS instances on the dedicated host are migrated to another host when a DDH failure occurs. If the automatic instance migration feature is disabled and your dedicated host fails, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for a new dedicated host.

**Note:** After all the ECS instances on a failed dedicated host are migrated to another dedicated host, the host ID and the metadata of the ECS instances remain unchanged. The metadata includes the ID, private IP address, and public IP address of each ECS instance. However, the machine ID of the dedicated host is changed.

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  Modify the settings of automatic instance migration.

    1.  Find the dedicated host that you want to modify. In the **Host ID/Name** column, move the pointer over the name or ID of the dedicated host. Click the ![Modify the information of the dedicated host](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2466546061/p131478.png) icon next to the name of the dedicated host.

    2.  In the **Modify DDH Information** dialog box, modify the settings of the automatic instance migration for the dedicated host.

        Turn on or turn off the **Action on Maintenance** switch to enable or disable the **automatic instance migration** feature.

    3.  Click **OK**.


In the **Actions** column, choose **Details** \> **Details** to view the modification result.

![View the modification result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8653909951/p48151.png)

