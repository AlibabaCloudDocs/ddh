# 设置CPU超卖比

部分DDH规格支持设置CPU超卖比。对于CPU绝对稳定性要求不严苛或者CPU负载不高的场景，提升超卖比可以提升可用vCPU数，用于部署更多同等规格的ECS实例，降低单位部署成本。

-   DDH为自定义规格（g6s、c6s、r6s）。更多信息，请参见[宿主机规格](/cn.zh-CN/产品简介/宿主机规格.md)。
-   DDH上的ECS实例全部处于**已停止**状态。

## 操作步骤

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。

2.  在左侧导航栏，单击**实例与镜像** \> **专有宿主机 DDH**。

3.  在顶部菜单栏左上角处，选择地域。

4.  选中待设置的DDH，在页面左上方，选择![dropdown-menu](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1713018061/p199068.png)\>**修改主机信息**。

    ![modify-ratio](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1991718061/p201716.png)

5.  在**编辑宿主机信息**对话框，输入CPU超卖比。

    CPU超卖比取值范围为1~5。一台DDH的可用vCPU数 = 物理CPU核数 \* 2 \* CPU超卖比。例如，g6s的物理CPU核数为52，如果设置CPU超卖比为4，则DDH创建完成后vCPU总数显示为416。

    ![input-ratio](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1991718061/p201718.png)

6.  单击**确定**。


**相关文档**  


[ModifyDedicatedHostAttribute](/cn.zh-CN/API参考/专有宿主机/ModifyDedicatedHostAttribute.md)

