# Automatic instance migration upon DDH failures

A dedicated host is based on a physical server. The dedicated host may shut down if a failure occurs on the physical server. To minimize the impact of physical failures on your business, Alibaba Cloud supports automatic instance migration upon DDH failures.

You can enable the automatic instance migration feature when or after you create a dedicated host.

-   If you want to enable the automatic instance migration feature when you create a dedicated host, log on to the Elastic Compute Service \(ECS\) console. In the left-side navigation pane, choose Instances & Images \> Dedicated Hosts. In the top navigation bar, select a region, and click Create DDH. On the page that appears, select **Automatic Instance Migration upon DDH Failure** in the **DDH Settings** section. For information about how to create a dedicated host, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).
-   For information about how to modify the configurations of automatic instance migration upon DDH failure, see [Modify the settings of automatic instance migration for a dedicated host](/intl.en-US/User Guide/Modify DDH settings/Modify the settings of automatic instance migration for a dedicated host.md).

**Note:** You cannot perform manual migration of ECS instances on local SSD dedicated hosts such as Local SSD type i2 upon DDH failure. In addition, you cannot perform automatic migration of ECS instances on local SSD dedicated hosts. If local SSD dedicated hosts fail, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for manual migration. However, the data in the local disk is lost after migration.

After the automatic instance migration feature is enabled for a dedicated host, the ECS instances on the dedicated host are migrated to another host if a DDH failure occurs. If the automatic instance migration feature is disabled and your dedicated host fails, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/overview) to apply for a new dedicated host.

**Note:** After all the ECS instances on a failed dedicated host are migrated to another dedicated host, the host ID and the metadata of the ECS instances remain unchanged. The metadata includes the ID, private IP address, and public IP address of each ECS instance. However, the machine ID of the dedicated host is changed.

