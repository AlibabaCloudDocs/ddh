# DDH故障迁移

一台DDH基于一台指定的物理服务器，可能会因为故障而自动停机。为了降低物理故障对您业务的影响，阿里云为您提供DDH故障迁移服务。

您可以在创建DDH时或创建DDH后配置DDH故障迁移。

-   创建DDH时，在**其他设置**区域，选中**宿主机故障时自动迁移**。创建DDH的详细步骤，请参见[创建DDH](/intl.zh-CN/快速入门/创建DDH.md)。
-   创建DDH后，修改DDH故障迁移配置的步骤，请参见[修改DDH故障迁移配置](/intl.zh-CN/用户指南/修改DDH相关设置/修改DDH故障迁移配置.md)。

**说明：** 本地SSD型DDH（例如本地SSD型i2）不支持自行手动迁移和故障时自动迁移。如果本地SSD型DDH出现故障，您可以[提交工单](https://workorder-intl.console.aliyun.com/#/overview)申请人工迁移，但迁移后本地盘数据会丢失。

故障迁移服务开启后，当DDH因故障停机时，会自动迁移至健康的DDH。若您未开启DDH故障迁移服务，DDH发生故障停机后，您需要[提交工单](https://workorder-intl.console.aliyun.com/#/overview)申请置换一台健康的DDH。

**说明：** DDH因故障迁移完成后，DDH ID及ECS实例的元数据（比如实例ID、私有IP地址、公网IP地址）均保持不变，但是由于更换了物理服务器，DDH的机器码会改变。

