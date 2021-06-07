# FAQ for ECS instances on dedicated hosts

This topic provides answers to frequently asked questions \(FAQ\) about Elastic Compute Service \(ECS\) instances that are created on dedicated hosts.

-   [What are the differences between ECS instances created on a dedicated host and ECS instances created on a shared host?](#comparison)
-   [What are the limits on the ECS instances created on a dedicated host?](#limits)
-   [Can I create different types of ECS instances on a dedicated host?](#ecsInstance)
-   [Can I create an ECS instance on a specified dedicated host?](#createEcsInstance)
-   [Can I migrate ECS instances between different dedicated hosts?](#ecsMigrationDdh)
-   [Can I adjust the specifications of ECS instances on a dedicated host?](#section_890_61o_yan)

## What are the differences between ECS instances created on a dedicated host and ECS instances created on a shared host?

ECS instances created on a dedicated host and ECS instances created on a shared host differ in the following ways:

-   Features: ECS instances connected over a classic network cannot be created on a dedicated host. For other differences in features, see [Comparisons of ECS instances on a dedicated host and a shared host](/intl.en-US/Product Introduction/Features/Comparisons of ECS instances on a dedicated host and a shared host.md).
-   Performance: They have similar performance except that the physical server on which the dedicated host is deployed is exclusive to you.

## What are the limits on the ECS instances created on a dedicated host?

ECS instances connected over a classic network cannot be created on a dedicated host. The billing method of a dedicated host limits the ECS instance types that you can create. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).

## Can I create different types of ECS instances on a dedicated host?

Yes. If the dedicated host has sufficient resources, you can create ECS instances of the types that match the dedicated host type. For example, you can create ECS instances of the g6t instance family on a Security-enhanced general type g6t dedicated host. However, you cannot create ECS instances of other instance families. For more information, see [Dedicated host types](/intl.en-US/Product Introduction/Dedicated host types.md).

## Can I create an ECS instance on a specified dedicated host?

Yes. You can create an ECS instance on a specified dedicated host in the ECS console. For more information, see [Create ECS instances on a dedicated host](/intl.en-US/Quick Start/Create ECS instances on a dedicated host.md).

## Can I migrate ECS instances between different dedicated hosts?

Yes. You can migrate ECS instances between dedicated hosts of the same type, except for dedicated hosts that have local SSD disks attached. For more information, see [Migrate ECS instances between different dedicated hosts](/intl.en-US/User Guide/Migrate ECS instances/Migrate ECS instances between different dedicated hosts.md).

## Can I adjust the specifications of ECS instances on a dedicated host?

Yes. If the specifications of ECS instances are no longer suitable for your business, you can adjust the specifications or modify the public bandwidth. For more information, see [t1836068.md\#](/intl.en-US/User Guide/O&M of dedicated hosts/Upgrade or downgrade a subscription ECS instance.md).

