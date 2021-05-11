# DDH上的ECS实例FAQ

本文介绍与DDH上的ECS实例相关的问题及解决方案。

-   [在DDH和共享宿主机上创建的ECS实例有什么区别？](#comparison)
-   [在DDH上创建ECS实例有什么限制吗？](#limits)
-   [能在同一台DDH上创建不同规格的ECS实例吗？](#ecsInstance)
-   [能指定一台DDH创建ECS实例吗？](#createEcsInstance)
-   [能在不同的DDH之间迁移ECS实例吗？](#ecsMigrationDdh)
-   [DDH上的ECS实例是否支持升降配功能？](#section_890_61o_yan)

## 在DDH和共享宿主机上创建的ECS实例有什么区别？

DDH上的ECS实例和共享宿主机上的ECS实例存在以下区别：

-   功能方面：DDH不支持创建经典网络ECS实例。其他功能差异，请参见[ECS实例功能对比](/cn.zh-CN/产品简介/功能特性/ECS实例功能对比.md)。
-   性能方面：基本一致。但是DDH是单租户环境，DDH所在物理服务器由您独享。

## 在DDH上创建ECS实例有什么限制吗？

DDH上不能创建经典网络类型的ECS实例。DDH的计费方式会限制您能创建的ECS实例规格，详情请参见[使用限制](/cn.zh-CN/产品简介/使用限制.md)。

## 能在同一台DDH上创建不同规格的ECS实例吗？

能。只要DDH资源容量允许，您能在一台DDH上创建与DDH规格匹配的任何ECS实例。比如，在一台安全增强通用型g6t规格的DDH上，您能创建g6t规格族内任意规格的ECS实例，但是不能创建其他规格族的ECS实例。DDH规格详情，请参见[宿主机规格](/cn.zh-CN/产品简介/宿主机规格.md)。

## 能指定一台DDH创建ECS实例吗？

能。您能通过ECS管理控制台在指定的DDH上创建ECS实例。更多详情，请参见[在DDH上创建ECS实例](/cn.zh-CN/快速入门/在DDH上创建ECS实例.md)。

## 能在不同的DDH之间迁移ECS实例吗？

能。您能在同一账号下相同主机规格的DDH之间迁移ECS实例，但是不包括本地SSD型DDH。具体操作，请参见[在不同DDH之间迁移ECS实例](/cn.zh-CN/用户指南/迁移ECS实例/在不同DDH之间迁移ECS实例.md)。

## DDH上的ECS实例是否支持升降配功能？

支持。当DDH上的ECS实例配置不再适用于您的业务需求时，您可以通过升级或降级实例规格、修改公网带宽的方式进行调整。更多详情，请参见[t1836068.md\#](/cn.zh-CN/用户指南/DDH运维/升降配包年包月ECS实例.md)。

