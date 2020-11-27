# DDH FAQ

This topic provides answers to frequently asked questions about Dedicated Host \(DDH\).

-   [What is DDH?](#section_1)
-   [What are the benefits of DDH?](#section_2)
-   [What scenarios does DDH apply to?](#section_3)
-   [Is DDH a bare metal service?](#section_4)
-   [What is the difference between a dedicated host and an ECS Bare Metal Instance \(EBM\)?](#section_5)
-   [How can I create and release a dedicated host?](#section_6)
-   [How can I check the available resources of a dedicated host?](#section_7)
-   [Can I migrate ECS instances from a shared host to a dedicated host?](#section_8)
-   [How can I use bring your own licenses \(BYOLs\) on a dedicated host?](#section_9)
-   [Does a dedicated host have a unique ID?](#section_10)
-   [Does Alibaba Cloud use the same machine code on different dedicated hosts?](#section_11)
-   [Will the instances on a dedicated host be automatically migrated to another dedicated host in the event of a failure?](#section_12)
-   [How do I select disks and public bandwidth when I purchase a dedicated host?](#section_3r6_0wx_15d)
-   [What can I do if packets are lost during User Datagram Protocol \(UDP\) communication?](#section_zya_hqb_gyz)

## What is DDH?

Alibaba Cloud DDH is a single-tenant hosting service. The physical resources of a dedicated host are used by only one tenant. Dedicated hosts of different tenants are isolated at the physical server level. You can create Elastic Compute Service \(ECS\) instances on a dedicated host. For more information, see [What is DDH?](/intl.en-US/Product Introduction/What is DDH?.md)

## What are the benefits of DDH?

You can bind an existing software license to an ECS instance created on a dedicated host. The ECS instance can be a Microsoft Windows Server instance or Microsoft Windows SQL Server instance. This reduces the cost of migrating your business to the cloud. DDH provides flexibility, visibility, and control when you deploy your applications. This ensures that your applications meet strict compliance and regulatory requirements. For more information, see [Benefits](/intl.en-US/Product Introduction/Benefits.md).

## What scenarios does DDH apply to?

For information about the scenarios to which DDH applies, see [Scenarios](/intl.en-US/Product Introduction/Scenarios.md).

## Is DDH a bare metal service?

No, DDH is not a bare metal service. The ECS instances deployed on a dedicated host are the same as the ECS instances deployed on a shared host.

## What is the difference between a dedicated host and an ECS Bare Metal Instance \(EBM\)?

A dedicated host is a cloud server that is created based on the virtualization technology. EBM is a computing service that combines the elasticity of virtual machines and the performance and features of physical machines. EBM was developed by Alibaba Cloud based on the state-of-the-art virtualization 2.0 technology. For more information, see [ECS Bare Metal Instance](/intl.en-US/Instance/Instance type families/ECS bare metal instance type family/ECS Bare Metal Instance.md).

## How can I create and release a dedicated host?

You can use the ECS console to create a dedicated host. For more information, see [Create a dedicated host](/intl.en-US/Quick Start/Create a dedicated host.md).

If a subscription dedicated host expires and is not renewed within a required period, the host is automatically released. For more information, see [Subscription](/intl.en-US/Pricing/Subscription.md).

## How can I check the available resources of a dedicated host?

You can check the total resources and available resources of a dedicated host by using the following methods:

-   For information about the total resources provided by dedicated hosts of various specifications, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).
-   To check the available resources of running dedicated hosts, log on to the ECS console. For more information, see [View the resources of a dedicated host](/intl.en-US/User Guide/View the resources of a dedicated host.md).

## Can I migrate ECS instances from a shared host to a dedicated host?

Yes, you can migrate ECS instances from a shared host to a dedicated host if both hosts belong to the same account. You can log on to the ECS console to migrate the ECS instances. After you restart the ECS instances, the instances are deployed on the destination dedicated host. However, you cannot migrate subscription ECS instances or preemptible instances. For more information, see [Migrate ECS instances from a shared host to a dedicated host](/intl.en-US/User Guide/Migrate ECS instances from a shared host to a dedicated host.md).

## How can I use bring your own licenses \(BYOLs\) on a dedicated host?

To use BYOLs on a dedicated host, perform the following steps:

1.  Check the terms and conditions of your BYOLs to confirm that you can use the licenses on a dedicated host. We recommend that you consult a licensing advisor to better understand the licensing requirements. After you confirm that you can use the license on a dedicated host, proceed to Step 2.
2.  Use the ECS console or call the ImportImage operation to import custom images. You can also download the software after you establish a remote connection to an ECS instance. For more information, see [Connect to an ECS instance]().
3.  Log on to your dedicated host and start the ECS instance that uses these images. When you run the instance, you may need to use Key Management Service \(KMS\) to activate the instance or software. For more information, see [What is KMS?](/intl.en-US/Product Introduction/What is KMS?.md).
4.  When you use BYOLs on a dedicated host, you may need to submit an audit table to your license provider. The DDH parameters such as the number of sockets, number of physical CPU cores, and number of vCPUs are required in the table. You can view these parameters in the ECS console.

## Does a dedicated host have a unique ID?

Yes, each dedicated host has a machine code. This code is similar to the asset ID of a physical server, but not the host ID. You can use this machine code to identify a dedicated host. A dedicated host assigned to your account has a machine code that corresponds to a physical server. This ensures easy filing of your assets.

## Does Alibaba Cloud use the same machine code on different dedicated hosts?

No, Alibaba Cloud does not use the same machine code on different dedicated hosts. Each machine code corresponds to only one physical server. If you are assigned a new physical server due to warranty expiration or migration, a new machine code is assigned to your dedicated host.

## Will the instances on a dedicated host be automatically migrated to another dedicated host in the event of a failure?

Alibaba Cloud DDH supports automatic failover. If you enable the feature, the instances are automatically migrated to another dedicated host if the current host fails. For more information, see [Modify the settings of automatic instance migration for a dedicated host](/intl.en-US/User Guide/Modify the settings of automatic instance migration for a dedicated host.md).

## How do I select disks and public bandwidth when I purchase a dedicated host?

You do not need to select disks or public bandwidth when you create a dedicated host. You must select disks and public bandwidth when you create an ECS instance on the dedicated host. For more information, see [Create ECS instances on a dedicated host](/intl.en-US/Quick Start/Create ECS instances on a dedicated host.md).

## What can I do if packets are lost during User Datagram Protocol \(UDP\) communication?

If UDP communication is implemented between various ECS instances on a host, the checksum value obtained on the send side may be wrong. UDP drops packets on the receive side if it detects inconsistent checksum values.

You can run the `ethtool -k ethx tx off` command to disable the checksum offload feature for the gateway on the send-side ECS instance.

**Note:** ethx indicates the gateway used during the UDP communication between ECS instances. Specify the value based on your needs.

