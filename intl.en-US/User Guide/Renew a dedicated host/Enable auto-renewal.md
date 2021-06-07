# Enable auto-renewal

To prevent a subscription dedicated host from being accidentally released when you forget to renew it, you can enable auto-renewal for the dedicated host. After you enable auto-renewal, the system automatically renews the dedicated host at the specified time. This topic describes how to enable auto-renewal. Auto-renewal can be enabled when you create a dedicated host or after.

The subscription dedicated host is not in the **Expired** state. For more information, see [Lifecycle of dedicated hosts](/intl.en-US/Product Introduction/Features/Lifecycle of dedicated hosts.md).

If you enable auto-renewal for a dedicated host, fees are deducted from your credit card or PayPal account on the expiration date. If fees fail to be deducted, the system attempts to deduct the fees 6 days and 14 days after the expiration date until the renewal is successful. However, if the renewal fails all three times, the dedicated host is stopped.

You can enable the auto-renewal feature when you create a dedicated host or after.

-   [Enable auto-renewal when you create a dedicated host](#section_09s_79j_8nr)
-   [Enable auto-renewal after you create a dedicated host](#section_kfy_02y_gbu)

## Enable auto-renewal when you create a dedicated host

For more information, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

The billing cycle of a subscription dedicated host depends on the subscription duration that was selected when you purchased the dedicated host:

-   If a dedicated host is purchased on a yearly basis, its billing cycle is one year.
-   If a dedicated host is purchased on a monthly basis, its billing cycle is one month.
-   If a dedicated host is purchased on a weekly basis, its billing cycle is one week.

## Enable auto-renewal after you create a dedicated host

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  Select the dedicated host for which you want to enable auto-renewal. Move the pointer over the ![More icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0484703261/p265427.png) icon next to **Renew** and click **Change Renew Settings**.

5.  In the Change Renew Settings dialog box, perform the following steps:

    1.  Turn on the **Enable Auto Renew** switch.

    2.  Select an auto-renewal duration from the **Duration** list.

    3.  Click **Confirm**.

    ![Auto-renewal](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1406772261/p265405.png)


