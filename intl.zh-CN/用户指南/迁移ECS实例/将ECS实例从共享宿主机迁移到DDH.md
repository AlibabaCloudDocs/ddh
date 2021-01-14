# 将ECS实例从共享宿主机迁移到DDH

您可以根据业务需要，将共享宿主机上的ECS实例迁移到指定DDH上，灵活部署业务。

-   待迁移ECS实例必须满足以下条件：
    -   如果需要停机后迁移ECS实例，必须提前停止ECS实例。具体操作，请参见[停止实例](/intl.zh-CN/实例/管理实例/停止实例.md)。

        **说明：** 停止实例会中断您的业务，请谨慎操作。

    -   计费方式为按量付费，且不能是抢占式实例。包年包月实例必须先转成按量付费实例，具体操作，请参见[包年包月转按量付费](/intl.zh-CN/产品定价/转换计费方式/包年包月转按量付费.md)。
-   目标DDH必须满足以下条件：
    -   与待迁移ECS实例属于同一账号、同一地域和可用区。
    -   可用资源满足待迁移ECS实例的要求。关于如何查看DDH的可用资源，请参见[查看DDH详细信息](/intl.zh-CN/用户指南/查看DDH相关资源/查看DDH资源.md)。
    -   支持您需要的实例规格族。更多信息，请参见[宿主机规格](/intl.zh-CN/产品简介/宿主机规格.md)。

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。

2.  在顶部菜单栏左上角处，选择地域。

3.  在左侧导航栏，单击**实例与镜像** \> **实例**。

4.  在**实例列表**页面，查看ECS实例所在的宿主机。

    1.  在页面右上角，单击![display-config](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6634341061/p171315.png)。

        ![config-icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201815.png)

    2.  选中**宿主机**，然后单击**确定**。

    3.  在**宿主机**区域，查看ECS实例所在的宿主机。

        -   显示DDH的ID和名称，说明ECS实例运行在DDH上。
        -   显示**系统分配**，说明ECS实例运行在共享宿主机上。
        ![host-column](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201816.png)

5.  找到待迁移ECS实例，然后在**操作**区域单击**更多** \> **实例设置** \> **调整宿主机部署**。

    ![modify-ddh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201817.png)

6.  在**调整宿主机部署**对话框，完成目标DDH相关设置。

    |配置项|说明|
    |:--|:-|
    |**目标宿主机**|在目标DDH列表中选择ECS实例要迁入的DDH。 **说明：** 如果您账号下没有满足迁移条件的DDH，则目标DDH列表为空。 |
    |**目标实例规格**|    -   如果停机后迁移ECS实例，您可以在迁移ECS实例的同时变更实例规格，支持的实例规格和目标DDH的规格有关。

![predefined-ddh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201824.png)

    -   如果不停机直接迁移ECS实例，必须选择相同的实例规格。

![same-instancetype](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2444718061/p201828.png) |
    |**关联宿主机**|选择ECS实例是否固定部署在目标DDH上。     -   **是**：固定部署在目标DDH上。ECS实例停机并释放资源后，再次启动时必须部署在该DDH上。若该DDH的可用资源不足，则ECS实例启动失败。
    -   **否**：不固定部署在目标DDH上。ECS实例停机并释放资源后，再次启动时优先部署在该DDH上。若该DDH的可用资源不足，则系统从允许自动部署的DDH中自动选择一台DDH部署该ECS实例。 |
    |**热迁移**|支持以下方式：    -   停机后迁移ECS实例。
    -   不停机直接迁移ECS实例。

**说明：** 直接迁移ECS实例时不支持同步变更实例规格。 |

7.  单击**确定**。

    您可以刷新**实例列表**页面，查看**宿主机**区域的显示是否已更新为目标DDH的ID和名称。

    ![shared-2-ddh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3045018061/p199694.png)


**相关文档**  


[ModifyInstanceDeployment](/intl.zh-CN/API参考/专有宿主机/ModifyInstanceDeployment.md)

