# 修改DDH故障迁移配置

为了降低物理故障对您业务的影响，阿里云为您提供DDH故障迁移服务。本章节介绍如何修改DDH故障迁移配置。

您可以在创建DDH时或创建DDH后配置DDH故障迁移。

-   创建DDH时，在**其他设置**区域，选中**宿主机故障时自动迁移**。创建DDH的详细步骤，请参见[创建DDH](/intl.zh-CN/快速入门/创建DDH.md)。
-   创建DDH后，修改DDH故障迁移配置的步骤，请参见[修改DDH故障迁移配置](/intl.zh-CN/用户指南/修改DDH相关设置/修改DDH故障迁移配置.md)。

**说明：** 本地SSD型DDH（例如本地SSD型i2）不支持自行手动迁移和故障时自动迁移。如果本地SSD型DDH出现故障，您可以[提交工单](https://workorder-intl.console.aliyun.com/#/overview)申请人工迁移，但迁移后本地盘数据会丢失。

故障迁移服务开启后，当DDH因故障停机时，会自动迁移至健康的DDH。若您未开启DDH故障迁移服务，DDH发生故障停机后，您需要[提交工单](https://workorder-intl.console.aliyun.com/#/overview)申请置换一台健康的DDH。

**说明：** DDH因故障迁移完成后，DDH ID及ECS实例的元数据（比如实例ID、私有IP地址、公网IP地址）均保持不变，但是由于更换了物理服务器，DDH的机器码会改变。

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。

2.  在左侧导航栏，单击**实例与镜像** \> **专有宿主机 DDH**。

3.  在顶部菜单栏左上角处，选择地域。

4.  修改故障迁移配置。

    1.  找到目标DDH，在**宿主机ID/名称**列中，将鼠标悬浮至宿主机ID或名称，然后单击宿主机名称右侧的![编辑宿主机属性](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9653909951/p131478.png)图标。

    2.  在**编辑宿主机信息**对话框，根据需要修改DDH故障迁移配置。

        打开**自动宕机迁移**开关即开启故障迁移，关闭**自动宕机迁移**开关即关闭故障迁移。

    3.  单击**确定**。


修改故障迁移配置后，在目标DDH**操作**列，单击**详细信息** \> **宿主机信息**查看修改结果。

![查看宕机迁移状态](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9653909951/p48151.png)

