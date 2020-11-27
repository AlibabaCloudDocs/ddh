# API概览

专有宿主机提供以下相关API接口。

|API|描述|
|---|--|
|[AllocateDedicatedHosts](/intl.zh-CN/API参考/专有宿主机/AllocateDedicatedHosts.md)|调用AllocateDedicatedHosts创建一台或多台包年包月专有宿主机。专有宿主机DDH是由单租户独享的物理机资源，您可以在专有宿主机上自行创建ECS实例和获取物理服务器属性信息等。|
|[DescribeDedicatedHostTypes](/intl.zh-CN/API参考/专有宿主机/DescribeDedicatedHostTypes.md)|调用DescribeDedicatedHostTypes查询指定地域下支持的专有宿主机规格详细参数，或者查询专有宿主机支持的ECS实例规格族。|
|[DescribeDedicatedHosts](/intl.zh-CN/API参考/专有宿主机/DescribeDedicatedHosts.md)|调用DescribeDedicatedHosts查询一台或多台专有宿主机的详细信息，包括专有宿主机的物理性能指标、虚拟机器码、使用状态和已创建的ECS实例列表等。|
|[DescribeDedicatedHostAutoRenew](/intl.zh-CN/API参考/专有宿主机/DescribeDedicatedHostAutoRenew.md)|调用DescribeDedicatedHostAutoRenew查询一台或多台包年包月专有宿主机自动续费状态。|
|[ModifyDedicatedHostAttribute](/intl.zh-CN/API参考/专有宿主机/ModifyDedicatedHostAttribute.md)|调用ModifyDedicatedHostAttribute修改一台专有宿主机的部分信息，包括专有宿主机的名称、描述和服务不可用属性等。|
|[ModifyDedicatedHostAutoRenewAttribute](/intl.zh-CN/API参考/专有宿主机/ModifyDedicatedHostAutoRenewAttribute.md)|调用ModifyDedicatedHostAutoRenewAttribute为一台或多台包年包月专有宿主机设置自动续费，也可以取消已设定的自动续费。|
|[ModifyDedicatedHostAutoReleaseTime](/intl.zh-CN/API参考/专有宿主机/ModifyDedicatedHostAutoReleaseTime.md)|调用ModifyDedicatedHostAutoReleaseTime为一台按量付费专有宿主机设定自动释放时间，或者取消自动释放一台按量付费专有宿主机。|
|[ModifyInstanceDeployment](/intl.zh-CN/API参考/专有宿主机/ModifyInstanceDeployment.md)|调用ModifyInstanceDeployment修改ECS实例的宿主机。ECS实例与目标宿主机必须位于同一地域。|
|[ModifyDedicatedHostsChargeType](/intl.zh-CN/API参考/专有宿主机/ModifyDedicatedHostsChargeType.md)|调用ModifyDedicatedHostsChargeType修改专有宿主机的付费类型。|
|[ReleaseDedicatedHost](/intl.zh-CN/API参考/专有宿主机/ReleaseDedicatedHost.md)|调用ReleaseDedicatedHost释放一台按量付费专有宿主机。|
|[RenewDedicatedHosts](/intl.zh-CN/API参考/专有宿主机/RenewDedicatedHosts.md)|调用RenewDedicatedHosts续费一台或者多台包年包月专有宿主机。|
|[RedeployDedicatedHost](/intl.zh-CN/API参考/专有宿主机/RedeployDedicatedHost.md)|调用RedeployDedicatedHost执行专有宿主机的故障迁移。|

