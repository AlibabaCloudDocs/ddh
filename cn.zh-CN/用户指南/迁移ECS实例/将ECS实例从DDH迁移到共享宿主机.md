# 将ECS实例从DDH迁移到共享宿主机

您可以根据业务需要，将DDH上的ECS实例迁移到共享宿主机上，灵活部署业务。

待迁移ECS实例必须满足以下条件：

-   已停止ECS实例。具体操作，请参见[停止实例](/cn.zh-CN/实例/管理实例/停止实例.md)。

    **说明：** 停止实例会中断您的业务，请谨慎操作。

-   计费方式为按量付费。包年包月实例必须先转成按量付费实例，具体操作，请参见[包年包月转按量付费](/cn.zh-CN/产品计费/转换计费方式/包年包月转按量付费.md)。
-   不是本地SSD型实例。

ECS实例从DDH迁移到共享宿主机后，您需要单独为计算资源（vCPU和内存）付费，DDH不再覆盖这部分费用，请保证账户额度充足。更多信息，请参见[按量付费](/cn.zh-CN/产品计费/计费方式/按量付费.md)。

## 操作步骤

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。

2.  在左侧导航栏，选择**实例与镜像** \> **专有宿主机 DDH**。

3.  在顶部菜单栏左上角处，选择地域。

4.  在**专有宿主机**页面，找到待迁移ECS实例所在的DDH，然后在**操作**区域单击**详细信息**。

    ![detail-info](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9313718061/p201811.png)

5.  找到待迁移ECS实例，在**操作**区域单击**调整宿主机部署**。

    ![modify-ddh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9313718061/p201812.png)

6.  在**调整宿主机部署**对话框，完成相关设置。

    |配置项|说明|
    |:--|:-|
    |**目标宿主机**|选择**共享宿主机**。|
    |**目标实例规格**|输入目标实例规格的名称，例如ecs.g6.large，各实例规格的特性和指标请参见[实例规格族](/cn.zh-CN/实例/实例规格族.md)。目标实例规格必须满足以下条件，否则会提示失败：

    -   支持从当前实例规格变配到目标实例规格，变配规则请参见[支持变配的实例规格](/cn.zh-CN/实例/升降配实例/支持变配的实例规格.md)。
    -   目标实例规格在DDH所在的可用区中仍有库存。 |

    ![2-sharedhost](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9555718061/p201840.png)

7.  单击**确定**。

    ECS实例迁移完成后自动启动，最终进入**运行中**状态。

8.  在**实例列表**页面，查看ECS实例所在的宿主机。

    1.  在页面右上角，单击![display-config](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6634341061/p171315.png)。

        ![config-icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201815.png)

    2.  选中**宿主机**，然后单击**确定**。

    3.  在**宿主机**区域，查看ECS实例所在的宿主机。

        -   显示DDH的ID和名称，说明ECS实例运行在DDH上。
        -   显示**系统分配**，说明ECS实例运行在共享宿主机上。
        ![host-column](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201816.png)


**相关文档**  


[ModifyInstanceDeployment](/cn.zh-CN/API参考/专有宿主机/ModifyInstanceDeployment.md)

