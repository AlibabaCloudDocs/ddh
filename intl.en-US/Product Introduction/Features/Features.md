# Features

A dedicated host \(DDH\) is a single-tenant physical server that runs on the Alibaba Cloud virtualization stack. This topic describes the features of DDH.

## Automatic deployment

The automatic deployment feature allows you to select a dedicated host to deploy Elastic Compute Service \(ECS\) instances. After you enable automatic deployment for a dedicated host, the dedicated host resides in the resource pool of your Alibaba Cloud account for automatic deployment. When you create ECS instances, you do not need to specify a dedicated host. The system selects a dedicated host from the resource pool to deploy the ECS instances. For more information about how to enable automatic deployment, see [Set the dedicated host to enable automatic deployment](/intl.en-US/User Guide/Modify DDH settings/Set the dedicated host to enable automatic deployment.md).

The following table describes the application scenarios for automatic deployment.

|Scenario|Operation|Result|Documentation|
|:-------|:--------|:-----|:------------|
|Create ECS instances.|Specify a dedicated host.|The ECS instances are deployed on the specified dedicated host.|-   Console operation:

[Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md)

-   API operation:

[CreateInstance](/intl.en-US/API Reference/Instances/CreateInstance.md) or [RunInstances](/intl.en-US/API Reference/Instances/RunInstances.md) |
|**Allow Automatic Deployment.**|ECS instances are automatically deployed.|
|Migrate ECS instances from a shared host to a dedicated host.|Specify a dedicated host.|The ECS instances are deployed on the specified dedicated host.|-   Console operation:

[Migrate ECS instances from a shared host to a dedicated host](/intl.en-US/User Guide/Migrate ECS instances/Migrate ECS instances from a shared host to a dedicated host.md)

-   API operation:

[ModifyInstanceDeployment](/intl.en-US/API Reference/Dedicated hosts/ModifyInstanceDeployment.md) |
|Specify no dedicated host.|ECS instances are automatically deployed.|-   Console operation:

The console does not support this operation.

-   API operation:

[ModifyInstanceDeployment](/intl.en-US/API Reference/Dedicated hosts/ModifyInstanceDeployment.md) |
|Migrate ECS instances among different dedicated hosts|Specify a dedicated host.|The ECS instances are deployed on the specified dedicated host.|-   Console operation:

[Migrate ECS instances between different dedicated hosts](/intl.en-US/User Guide/Migrate ECS instances/Migrate ECS instances between different dedicated hosts.md)

-   API operation:

[ModifyInstanceDeployment](/intl.en-US/API Reference/Dedicated hosts/ModifyInstanceDeployment.md) |
|Specify no dedicated host.|ECS instances are automatically deployed. **Note:** If the dedicated host where the ECS instances reside allows automatic deployment and has the most available resources, the instances are still deployed on the dedicated host.

|-   Console operation:

The console does not support this operation.

-   API operation:

[ModifyInstanceDeployment](/intl.en-US/API Reference/Dedicated hosts/ModifyInstanceDeployment.md) |

## Host association

Host association is suitable for ECS instances that have enabled the No Fees for Stopped Instances feature. You can specify whether instances are deployed on the original dedicated host after they are stopped or restarted. After the host is associated, the instances run on the same physical server even if they are stopped and restarted. This feature also helps you maintain the same deployment policy for ECS instances.

The following table describes how to use the host association feature.

|Scenario|Operation|Result|
|:-------|:--------|:-----|
|The ECS instances have enabled the No Fees for Stopped Instances feature. The instances are restarted after they are stopped.|Enable the host association feature. For more information, see [Associate an ECS instance with a dedicated host](/intl.en-US/User Guide/Modify DDH settings/Associate an ECS instance with a dedicated host.md).

|The ECS instances are still deployed on the original dedicated host. If the available resources of the original dedicated host are insufficient, the instance fails to be restarted.|
|Disable the host association feature. To disable this feature, set **Associate with DDH** to **No**. For more information, see ****[Associate with DDH](/intl.en-US/User Guide/Modify DDH settings/Associate an ECS instance with a dedicated host.md).

|The ECS instances are first deployed on the original dedicated host. However, if the available resources of the original dedicated host are insufficient, the system deploys the ECS instances on another dedicated host.|

## Resource efficiency

If the No Fees for Stopped Instances feature is enabled, the CPU and memory resources that are used by the instances are released after you stop the instances.

For more information, see [Host association](#section_0s4_rym_c1s).

## Instance upgrade and downgrade

You can change the configurations of the ECS instances that are created on a dedicated host. You can upgrade or downgrade the instance type, and adjust the public bandwidth of instances based on your business requirements. For more information, see [t1836068.md\#](/intl.en-US/User Guide/O&M of dedicated hosts/Upgrade or downgrade a subscription ECS instance.md).

