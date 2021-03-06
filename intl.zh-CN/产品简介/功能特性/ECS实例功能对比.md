# ECS实例功能对比

运行在专有宿主机DDH上的ECS实例与运行在共享宿主机上的ECS实例基本相同，仅部分功能存在差异。

存在差异的功能如下表所示。

|对比项|共享宿主机上的ECS实例|DDH上的ECS实例|
|:--|:-----------|:---------|
|网络类型|专有网络VPC和经典网络，详情请参见云服务器ECS[网络类型](/intl.zh-CN/网络/网络类型.md)。|专有网络VPC。|
|计费项|详情请参见[计费概述](/intl.zh-CN/产品定价/计费概述.md)。|详情请参见[DDH上的ECS资源计费](/intl.zh-CN/产品定价/DDH上的ECS资源计费.md)。|
|计费方式|包年包月、按量付费、抢占式实例、预留实例券。

|包年包月、按量付费。 |
|续费|根据需要设置续费时长。|实例续费后的到期时间不得晚于包年包月DDH的到期时间，详情请参见[使用限制](/intl.zh-CN/产品简介/使用限制.md)。|
|停机不收费|详情请参见[按量付费实例停机不收费](/intl.zh-CN/产品定价/计费方式/按量付费实例停机不收费.md)。|进入停机不收费模式后，实例停机会释放DDH资源（包括vCPU和内存），启动时再重新分配DDH资源。停机不收费模式下的资源计费详情，请参见[包年包月](/intl.zh-CN/产品定价/包年包月.md)。|
|按量付费转包年包月|详情请参见[按量付费转包年包月](/intl.zh-CN/产品定价/转换计费方式/按量付费转包年包月.md)，仅需符合功能限制条件。

|除了功能限制条件外，只适用于包年包月DDH，而且转换后ECS实例的过期时间不能晚于DDH的过期时间。|
|ECS实例规格|详情请参见[实例规格族](/intl.zh-CN/实例/实例规格族.md)。|DDH主机规格支持的预定义实例规格或自定义实例规格，详情请参见[宿主机规格](/intl.zh-CN/产品简介/宿主机规格.md)。|
|创建ECS实例|详情请参见[使用向导创建实例](/intl.zh-CN/实例/创建实例/使用向导创建实例.md)。|详情请参见[在DDH上创建ECS实例](/intl.zh-CN/快速入门/在DDH上创建ECS实例.md)。|
|变更实例规格|详情请参见[修改实例规格](/intl.zh-CN/实例/升降配实例/升降配方式概述.md)。|详情请参见[t1836068.md\#](/intl.zh-CN/用户指南/DDH运维/升降配包年包月ECS实例.md)。|
|调整公网带宽|详情请参见[修改公网带宽](/intl.zh-CN/实例/升降配实例/升降配方式概述.md)。|详情请参见[修改公网带宽](/intl.zh-CN/实例/升降配实例/升降配方式概述.md)。|
|创建后分配公网IP地址|详情请参见[修改公网带宽](/intl.zh-CN/实例/升降配实例/升降配方式概述.md)。|详情请参见[修改公网带宽](/intl.zh-CN/实例/升降配实例/升降配方式概述.md)。|
|释放实例|-   按量付费实例支持手动释放或自动释放。更多详情，请参见[释放实例](/intl.zh-CN/实例/管理实例/释放实例.md)。
-   包年包月实例到期或者按量付费实例欠费停机后未及时处理，实例会被自动释放。

|包年包月DDH到期后未及时处理，实例会被自动释放。|

