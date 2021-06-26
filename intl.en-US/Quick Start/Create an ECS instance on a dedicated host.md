# Create an ECS instance on a dedicated host

This topic describes how to create and configure an Elastic Compute Service \(ECS\) instance on a dedicated host.

Before you create an ECS instance on a dedicated host, the following prerequisites must be met:

-   A dedicated host is created. For more information, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).
-   The real-name verification is complete if you need to create an ECS instance for a region in mainland China. For more information, see [Real-name registration FAQs](https://www.alibabacloud.com/help/doc-detail/52595.htm).
-   An IPv4 virtual private cloud \(VPC\) is created in the region where the dedicated host resides. For more information, see [Create an IPv4 VPC](/intl.en-US/Quick Start/Create an IPv4 VPC.md).
-   A security group is created in the same region as the dedicated host and rules are added to the security group if you do not use the default security group. For more information, see [Create a security group](/intl.en-US/Security/Security groups/Create a security group.md) and [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).
-   An SSH key pair is created in the region where the dedicated host resides if you need to associate the SSH key pair with an ECS Linux instance. For more information, see [Create an SSH key pair](/intl.en-US/Security/Key pairs/Use an SSH key pair/Create an SSH key pair.md).
-   The user data of ECS instances are prepared if you need to configure the user data. For more information, see [Overview of ECS instance user data](/intl.en-US/Instance/Manage instances/Manage instance user data/Overview of ECS instance user data.md).
-   A Resource Access Management \(RAM\) RAM role is created for an ECS instance and authorized to access the ECS instance if you allow the instance to assume a RAM role. For more information, see [Bind an instance RAM role](/intl.en-US/Security/Instance RAM roles/Bind an instance RAM role.md).

Only VPC-connected ECS instances can be created on a dedicated host. The ECS instances on a dedicated host have different features from the ECS instances on a shared host. For more information, see [Comparisons of ECS instances on a dedicated host and a shared host](/intl.en-US/Product Introduction/Features/Comparisons of ECS instances on a dedicated host and a shared host.md).

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Dedicated Hosts**.

3.  In the top navigation bar, select a region.

4.  Find the dedicated host on which you want to create an ECS instance. Click **Create Instance** in the **Actions** column.

5.  Specify the required parameters in the **Basic Configurations** step.

    1.  Specify **Dedicated Host**.

        By default, the dedicated host that you previously selected on the Dedicated Hosts page is used. You can select another dedicated host.

    2.  Select or clear the **Associate with DDH** option. This option specifies whether the instance is still deployed on the current dedicated host if the instance is stopped, released, or restarted.

        -   If you select the **Associate with DDH** option, the instance is deployed on the current dedicated host. If the resources of the dedicated host are insufficient, the instance fails to be restarted.
        -   If you clear the **Associate with DDH** option, the instance is deployed on another dedicated host of your Alibaba Cloud account when the resources of the current dedicated host are insufficient. The dedicated host must be available for automatic instance deployment. For more information, see [Features](/intl.en-US/Product Introduction/Features/Features.md).
    3.  Specify **Billing Method**.

        Select a billing method for the ECS instances based on the billing method of the dedicated host. You can select **Subscription** or **Pay-As-You-Go** as the billing method of ECS instances that run on a subscription dedicated host.

    4.  Specify the type and quantity of the ECS instances.

        The region and zone of the ECS instance must be the same as those of the dedicated host. The available instance types depend on the type and available computing resources of the dedicated host. For more information, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).

        -   If the dedicated host supports only predefined instance types, click Predefined Instance Type. Then, select the instance type in the Instance Type section.

            ![ECS instance type](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3407906951/p100859.png)

        -   If the dedicated host supports custom instance types, click **Custom Instance Type**. Then, you can adjust the sliders to specify the number of vCPUs and the size of the memory. The minimum number of vCPUs is 1. If more than one vCPU are required, you must set this parameter to an even number, for example, 2 or 4. The minimum size of the memory is 1 GiB.

            ![Add a custom instance type](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1586864261/p271673.png)

    5.  Select an image for the instance.

        You can select a public image, custom image, shared image, or an image that is purchased from Alibaba Cloud Marketplace. For more information, see [Select an image](/intl.en-US/Images/Select an image.md).

        **Note:**

        -   To associate an SSH key pair with the ECS instance, you must select a Linux operating system from the drop-down list for the image.
        -   To configure user data of the instance, you must select an image that supports user data. For more information, see [Manage the user data of Linux instances](/intl.en-US/Instance/Manage instances/Manage instance user data/Manage the user data of Linux instances.md).
    6.  Select the storage for the instance.

        -   **System Disk**: Required. The system disk is used to install the operating system. You must specify the type and capacity of the system disk.
            -   Disk Type: All available types of disks in the current region are listed in this section.
            -   Capacity: The default capacity of the system disk is 40 GiB. The maximum capacity is 500 GiB. If the size of the selected image is larger than 40 GiB, the image size is the default value. The minimum size of the system disk is related to the image that you selected. The minimum size is displayed on the buy page.

                |Operating system image|System disk capacity \(GiB\)|
                |:---------------------|:---------------------------|
                |Linux \(excluding CoreOS and Red Hat Enterprise Linux\)|\[max\{20, image file size\}, 500\]|
                |FreeBSD|\[max \{30, image file size\}, 500\]|
                |CoreOS|\[max\{30, image size\}, 500\]|
                |Red Hat|\[max \{40, image file size\}, 500\]|
                |Windows|\[max\{40, image size\}, 500\]|

        -   **Data Disk**: To add data disks, you must specify the disk type, capacity, and quantity. You must also specify whether to enable **disk encryption**. You can add an empty data disk or use a snapshot to add a data disk.

            **Note:** The data disk has the following features:

            -   The billing method of the data disk is the same as that of the instance.
            -   When you enable or disable the Release Disk with Instance feature for a system disk or data disk, take note of the following items:
                -   When the Release Disk with Instance feature is enabled, the disk is automatically released when its attached ECS instance is released.
                -   When the Release Disk with Instance feature is disabled, the disk is retained as a pay-as-you-go data disk 15 days after its attached ECS instance expires, 15 days after a payment becomes overdue for the instance, or when the instance is manually released. If your disks are created in regions inside mainland China, you must complete real-name verification for your account to ensure that the disks can be retained.

                    **Note:** The retained data disk is billed on a pay-as-you-go basis. You can log on to the Billing Management console and view the consumption details based on the disk ID.

            -   A maximum of 16 data disks can be attached to a single instance. For more information, see the "Elastic Block Storage \(EBS\) limits" section in [Limits](/intl.en-US/Product Introduction/Limits.md).
        -   If you create an instance from an instance family with local SSDs, such as the i2 type, the information of the local SSDs is displayed and cannot be modified. For more information about the local SSDs of an instance family, see [Instance family](/intl.en-US/Instance/Instance family.md).
    7.  Click **Next: Networking**.

6.  Specify the parameters in the **Networking** step.

    1.  Specify **Network Type**.

        You can select only **VPC** as the network type. Select a VPC and vSwitch from the drop-down lists. If no VPC or vSwitch is created, you can use the default VPC or vSwitch.

    2.  Configure the public bandwidth.

        -   If you want to assign a public IP address to the instance, you must select **Assign Public IP Address**. Then, select **Pay-By-Traffic** or **Pay-By-Bandwidth** as the billing method of the public bandwidth, and specify the bandwidth. The public IP address cannot be detached from the instance. For more information about the billing method of public bandwidth, see [Public bandwidth](/intl.en-US/Pricing/Billing items/Public bandwidth.md).
        -   If your instance does not need to access the Internet or your VPC-type instance uses an elastic IP address \(EIP\) to access the Internet, you do not need to assign a public IP address. You can associate an EIP with or disassociate an EIP from an instance at any time.
    3.  Specify **Security Group**.

        Select a security group whose rules meet your business requirements.

        **Note:** If no security group is created, you can use the default security group. For more information, see [Default security group rules]().

    4.  Specify **Elastic Network Interface**.

        If the selected instance type supports Elastic Network Interface \(ENI\), you can add an ENI and select a vSwitch for the ENI.

        **Note:** By default, the ENI is released together with the instance. You can also call the [DetachNetworkInterface](/intl.en-US/API Reference/Elastic network interfaces/DetachNetworkInterface.md) operation to detach the ENI from the instance.

    5.  Click **Next: System Configurations**.

7.  Specify the parameters in the **System Configurations** step.

    1.  Select and configure **Logon Credentials**.

        You can specify a key pair and password. You can also select **Set Later** to configure the logon credential after the instance is created. Select a logon credential based on the operating system of the image.

        -   Linux: You can use a key pair or password as the logon credential.
        -   Windows: You can use only a password as the logon credential.
    2.  Specify **Instance Name** and **Host**.

    3.  Set the parameters in the **Advanced** section.

        -   RAM Role: You can assign a RAM role to the instance.
        -   User Data: You can customize the startup behavior of the instance or transfer data to the instance.
    4.  Click **Next: Grouping**.

8.  Specify the parameters in the **Grouping** step.

    -   If you have multiple instances, we recommend that you tag the instances for easy identification.
    -   If you are an enterprise user, and you have activated Resource Management and created resource groups, you can manage instances by using the resource groups.
9.  Confirm the order and create the ECS instances.

    1.  In the **Configurations Selected** section, confirm the configurations of the instances.

        You can click the ![Modify a configuration](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3407906951/p1347.png) icon to modify the configurations.

    2.  Configure the release or renewal of the ECS instances based on the billing method.

        -   If the billing method of the instances is **Subscription**, you must specify the duration, and specify whether to turn on the **Enable Auto-renewal** switch.

            **Note:** The expiration date of the subscription instances cannot be later than that of the subscription dedicated host.

        -   If the billing method of the instances is **Pay-As-You-Go**, you can select **Automatic Release** and specify the time to automatically release the instances.
    3.  Confirm the **Total** cost in the lower-right corner of the page. The total cost includes the cost of the image, data disks, and public bandwidth.

    4.  Read and accept the **ECS Terms of Service**.

    5.  Proceed based on the billing method of the ECS instances:

        -   If the billing method of the ECS instances is **Subscription**, click **Create Order**.
        -   If the billing method of the ECS instances is **Pay-As-You-Go**, click **Create Instance**.

After the instances are created, click **Console** in the upper-right corner of the page to go back to the ECS console. On the **Instances** page, select the region where the created instances reside. Then, you can view the instance ID, public IP address, and private IP address of the created instances. To view the information of the dedicated host where each ECS instance is created, perform the following operations: Click the **Column Filters** button. In the Column Filters dialog box, select the Dedicated Host option and click OK.

**Note:** For more information about **Column Filters**, see [Migrate ECS instances between different dedicated hosts](/intl.en-US/User Guide/Migrate ECS instances/Migrate ECS instances between different dedicated hosts.md).

-   You can use the FTP service to upload on-premises files to the ECS instances. For more information about how to deploy the FTP service, see [Build an FTP site on an ECS instance](/intl.en-US/Tutorials/Build an application/Build an FTP site on an ECS instance/Manually build an FTP site on a Windows instance.md).
-   After the ECS instances are created, we recommend that you check whether the operating systems are compliant and hardened. For more information, see the following topics:
    -   [Harden operating system security for Linux](https://www.alibabacloud.com/help/zh/faq-detail/49809.htm).
    -   [Harden operating system security for Windows](https://www.alibabacloud.com/help/faq-detail/49781.htm).
-   If you have added data disks during instance creation, the partitions of the data disks must be formatted before the data disks can be used. For more information, see [Format a data disk for a Linux instance](/intl.en-US/Block Storage/Cloud disks/Format a data disk/Format a data disk for a Linux instance.md) or [Format a data disk for a Windows ECS instance](/intl.en-US/Block Storage/Cloud disks/Format a data disk/Format a data disk for a Windows ECS instance.md).

**Related topics**  


[RunInstances](/intl.en-US/API Reference/Instances/RunInstances.md)

