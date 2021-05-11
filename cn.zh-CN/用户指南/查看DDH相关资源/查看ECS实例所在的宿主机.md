# 查看ECS实例所在的宿主机

ECS实例可以运行在DDH或者共享宿主机上，且支持在DDH之间、DDH和共享宿主机之间迁移ECS实例。本文介绍如何查看ECS实例所在的宿主机。

## 操作步骤

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。

2.  在左侧导航栏，选择**实例与镜像** \> **实例**。

3.  在顶部菜单栏左上角处，选择地域。

4.  在页面右上角，单击![display-config](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6634341061/p171315.png)。

    ![config-icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4089018061/p201601.png)

5.  在**自定义列表项**对话框，选中**宿主机**，然后单击**确定**。

6.  在**宿主机**列，查看ECS实例所在的宿主机。

    -   显示DDH的ID和名称，说明ECS实例运行在DDH上。
    -   显示**系统分配**，说明ECS实例运行在共享宿主机上。
    ![display-ddh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4089018061/p201603.png)


**相关文档**  


[DescribeInstances](/cn.zh-CN/API参考/实例/DescribeInstances.md)

[在不同DDH之间迁移ECS实例](/cn.zh-CN/用户指南/迁移ECS实例/在不同DDH之间迁移ECS实例.md)

[将ECS实例从共享宿主机迁移到DDH](/cn.zh-CN/用户指南/迁移ECS实例/将ECS实例从共享宿主机迁移到DDH.md)

[将ECS实例从DDH迁移到共享宿主机](/cn.zh-CN/用户指南/迁移ECS实例/将ECS实例从DDH迁移到共享宿主机.md)

