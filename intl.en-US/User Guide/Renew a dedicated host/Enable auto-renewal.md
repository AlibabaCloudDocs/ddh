# Enable auto-renewal

To avoid the accidental release of a subscription dedicated host when you forget to renew the subscription, you can enable auto-renewal for the dedicated host. Once you enable auto-renewal, the system automatically renews the subscription for the dedicated host. This topic describes how to enable auto-renewal. Auto-renewal can be enabled during and after you create a dedicated host.

The status of a subscription dedicated host cannot be **Expired**. For more information about the status of a dedicated host, see [Lifecycle of dedicated hosts](/intl.en-US/Product Introduction/Lifecycle of dedicated hosts.md).

After auto-renewal is enabled, the system automatically deducts the fee at 08:00:00 \(UTC+8\) 9 days before the expiration date of the dedicated host.

After auto-renewal is enabled, Alibaba Cloud automatically charges you for the renewal from your credit cards or PayPal accounts on the expiration date \(T\). If the fee deduction fails, the fee is deducted again 7 days \(T + 6\) and 15 days \(T + 14\) after the expiration until the renewal is successful. If the renewal fails all three times, the dedicated host is stopped.

You can enable the auto-renewal feature during and after you create a dedicated host.

-   [Enable auto-renewal when you create a dedicated host](#section_09s_79j_8nr)
-   [Enable auto-renewal after you create a dedicated host.](#section_kfy_02y_gbu)

## Enable auto-renewal when you create a dedicated host

For more information on how to enable auto-renewal when you create a dedicated host, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

If the auto-renewal feature is enabled when a dedicated host is created, the billing cycle is based on the subscription duration that is selected when you purchase the dedicated host:

-   For yearly subscriptions, the billing cycle is one year.
-   For monthly subscriptions, the billing cycle is one month.
-   For weekly subscriptions, the billing cycle is one week.

## Enable auto-renewal after you create a dedicated host.

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  Log on to the [ECS console](https://partners-intl.console.aliyun.com/#/ecs).

3.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

4.  In the top navigation bar, select a region.

5.  Select the target dedicated host. Choose **Actions** \> **Change Renew Settings**.

6.  In the Change Renew Settings dialog box, perform the following steps.

    1.  Turn on the **Enable Auto Renew** switch.

    2.  In the **Duration** list, select the auto-renewal duration.

    3.  Click **Confirm**.

    ![change_revew_settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3653909951/p63819.png)


