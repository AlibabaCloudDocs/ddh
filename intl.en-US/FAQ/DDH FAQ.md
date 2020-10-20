# DDH FAQ

This topic provides answers to commonly asked questions about Dedicated Host \(DDH\).

-   [What is DDH?](#section_1)
-   [What are the benefits of DDH?](#section_2)
-   [What are the scenarios where DDH is required?](#section_3)
-   [Is DDH a bare metal product?](#section_4)
-   [What is the difference between a dedicated host and an ECS Bare Metal Instance \(EBM\)?](#section_5)
-   [How can I create and release a dedicated host?](#section_6)
-   [How can I check the available resources of a dedicated host?](#section_7)
-   [Can I migrate ECS instances from a shared host to a dedicated host?](#section_8)
-   [How can I use bring your own licenses \(BYOLs\) on a dedicated host?](#section_9)
-   [Does a dedicated host have a unique ID?](#section_10)
-   [Does Alibaba Cloud use the same machine code on different dedicated hosts?](#section_11)
-   [Will the instances on a dedicated host be automatically migrated to another dedicated host in the event of a failure?](#section_12)
-   [How do I select disks and public bandwidth when I purchase a dedicated host?](#section_3r6_0wx_15d)

## What is DDH?

Alibaba Cloud DDH is a single-tenant hosting service. The physical resources of a dedicated host are dedicated for the use of only one tenant. Dedicated hosts of different tenants are isolated at the physical server level. You can create Elastic Compute Service \(ECS\) instances on a dedicated host. For more information, see [What is DDH?](/intl.en-US/Product Introduction/What is DDH?.md)

## What are the benefits of DDH?

You can bind an existing software license, such as Microsoft Windows Server and Microsoft Windows SQL Server, to an ECS instance that is created on a dedicated host. This reduces the cost of migrating your business to the cloud. DDH provides flexibility, visibility, and controllability when you deploy your applications. This ensures that your applications meet strict compliance and regulatory requirements. For more information, see [Benefits](/intl.en-US/Product Introduction/Benefits.md).

## What are the scenarios where DDH is required?

For information about the scenarios, see [Scenarios](/intl.en-US/Product Introduction/Scenarios.md).

## Is DDH a bare metal product?

No, DDH is not a bare metal product. The ECS instances that are deployed on a dedicated host are the same as the ECS instances that are deployed on a shared host.

## What is the difference between a dedicated host and an ECS Bare Metal Instance \(EBM\)?

A dedicated host is a cloud server that is created based on the virtualization technology. EBM is a computing service that combines the elasticity of virtual machines and the performance and features of physical machines. EBM is developed by Alibaba Cloud based on the state-of-the-art virtualization 2.0 technology. For more information about EBM, see [ECS Bare Metal Instances](/intl.en-US/Instance/Instance type families/ECS bare metal instance type family/ECS Bare Metal Instances.md).

## How can I create and release a dedicated host?

You can use the ECS console to create a dedicated host. For more information, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

If the subscription of a dedicated host expires and is not renewed within a required period, the host is automatically released. For more information, see [Subscription](/intl.en-US/Pricing/Subscription.md).

## How can I check the available resources of a dedicated host?

You can check the total resources and available resources of a dedicated host by using the following methods:

-   For information about the total resources that are provided by dedicated hosts of various specifications, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).
-   To check the available resources of running dedicated hosts, log on to the ECS console. For more information, see [View the resources of a dedicated host](/intl.en-US/User Guide/View the resources of a dedicated host.md).

## Can I migrate ECS instances from a shared host to a dedicated host?

Yes, you can migrate ECS instances from a shared host to a dedicated host if both hosts belong to the same account. You can log on to the ECS console to migrate the ECS instances. After you restart the ECS instances, the instances are deployed on the destination dedicated host. However, you cannot migrate subscription ECS instances or preemptible instances. For more information, see [Migrate ECS instances from a shared host to a dedicated host](/intl.en-US/User Guide/Migrate ECS instances from a shared host to a dedicated host.md).

## How can I use bring your own licenses \(BYOLs\) on a dedicated host?

To use BYOLs on a dedicated host, perform the following steps:

1.  Check the terms and conditions of your BYOLs to confirm that you can use the licenses on a dedicated host. We recommend that you consult a licensing advisor.
2.  Use the ECS console or call the ImportImage operation to import custom images. You can also download the software after you establish a remote connection to an ECS instance. For more information, see [Connect to an ECS instance]().
3.  Log on to your dedicated host and start the ECS instance that uses these images. When you run the instance, you may need to use Key Management Service \(KMS\) to activate the instance or software. For more information about KMS, see [What is KMS?](/intl.en-US/Product Introduction/What is KMS?.md)
4.  When you use BYOLs on a dedicated host, you may need to submit an audit table to your license provider. The DDH parameters such as the number of sockets, number of physical CPU cores, and number of vCPUs are required in the table. You can view these parameters in the ECS console.

## Does a dedicated host have a unique ID?

Yes, each dedicated host has a machine code \(similar to the asset ID of a physical server, but not the host ID\). You can use this machine code to identify a dedicated host. A dedicated host assigned to your account has a machine code that corresponds to a physical server. This ensures easy filing of your assets.

## Does Alibaba Cloud use the same machine code on different dedicated hosts?

No, Alibaba Cloud does not use the same machine code on different dedicated hosts. Each machine code corresponds to only one physical server. If you are assigned with a new physical server due to warranty expiration or migration, a new machine code is assigned to your dedicated host.

## Will the instances on a dedicated host be automatically migrated to another dedicated host in the event of a failure?

Alibaba Cloud DDH supports automatic failover. If you enable the feature, the instances are automatically migrated to another dedicated host when the current host fails. For more information, see [Modify the settings of automatic instance migration for a dedicated host](/intl.en-US/User Guide/Modify the settings of automatic instance migration for a dedicated host.md).

## How do I select disks and public bandwidth when I purchase a dedicated host?

You do not need to select disks or public bandwidth when you create a dedicated host. You must select disks and public bandwidth when you create an ECS instance on the dedicated host. For more information, see [Create ECS instances on a dedicated host](/intl.en-US/Quick Start/Create ECS instances on a dedicated host.md).

