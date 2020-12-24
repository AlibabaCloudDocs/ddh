# Set the dedicated host to enable automatic deployment

After you create a dedicated host, you can set the dedicated host to enable automatic deployment. The system automatically deploys ECS instances on a dedicated host. This topic describes how to enable automatic deployment for a dedicated host.

Make sure that you have created a dedicated host. For more information, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

After the dedicated host is set to enable automatic deployment, you do not need to specify a dedicated host when you create an ECS instance. The system automatically selects a dedicated host from the dedicated hosts that supports automatic deployment to deploy the instance. For more information about automatic deployment, see [Automatic deployment](/intl.en-US/Product Introduction/Features.md).

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  Select the target dedicated host.

5.  Choose **Actions** \> **Modify DDH Info**.

6.  In the Modify DDH Info dialog box, enable **Automatic Deployment**.

7.  Click **OK**.


In the **Automatic Deployment** column of the dedicated host, the value is changed to **On**.

You can use the automatic deployment feature to create ECS instances. The system automatically selects a dedicated host to deploy ECS instances. For more information, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).

