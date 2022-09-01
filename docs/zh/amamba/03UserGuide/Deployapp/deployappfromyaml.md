# 从 Yaml 部署应用

通过接入集群操作，能够对众多云服务平台集群和本地私有物理集群进行统一纳管，形成统一治理平台。有效避免了被厂商锁定风险。助力企业业务上云。

本节介绍如何接入外部集群，进行统一管理。

## 前提条件

1. 准备一个[已创建 Kubernetes](../../../kpanda/07UserGuide/Clusters/CreateCluster.md)的容器管理平台，且能够访问集群的 UI 界面。
2. 准备一个待接入的集群，且该集群网络通畅。

## 操作步骤

### 步骤 1  登录平台

`NS Edit` 用户根据下表的信息成功登录后，点击左上角的`集群列表`进入`集群列表`页面。

| 参数                    | 说明                                                         | 举例值                       |
| :---------------------- | :----------------------------------------------------------- | :--------------------------- |
| UI 账户和密码          | 【类型】必填<br />【含义】用来登录容器管理平台 Web UI 的管理员账户和密码 | 账户：root<br />密码：****** |
| 容器平台的 Web UI 地址 | 【类型】必填<br />【含义】容器管理平台的 Web UI 的 IP 地址   | 10.6.124.110                 |

### 步骤 2  基本信息配置

进入 `集群列表` 页面后，点击右上角的 `接入集群` 按钮，进入接入 `集群` 页面。

参照下表，对待接入集群的基本信息进行配置。

| 参数     | 说明                                                         | 举例值                                            |
| :------- | :----------------------------------------------------------- | :------------------------------------------------ |
| 集群名称 | 【类型】必填<br />【含义】待接入集群接入后的名称，该名称具有唯一性，设置后不可更改。<br />【注意】名称最大长度为 63 个字符，只能包含小写字母、数字及分隔符("-")，且必须以小写字母或数字开头及结尾。 | Cluster-Daocloud                                  |
| 集群别名 | 【类型】可选<br />【含义】待接入集群接入后的别名。<br />【注意】可输入任意字符，不超过 60 个字符。 | Deployment-Cluester                               |
| 集群厂商 | 【类型】可选<br />【含义】集群的发行厂商，包括市场主流云厂商和本地私有物理集群。<br />【注意】对于本地私有物理集群或列表中未显示的集群厂商，可选择其它厂商，自定义厂商名。 | Daocloud                                          |
| 集群标签 | 【类型】可选<br />【含义】为待接入集群添加标签。             | Namespace-01                                      |
| 集群注解 | 【类型】可选<br />【含义】为待接入集群添加注解。             | 2                                                 |
| 描述信息 | 【类型】可选<br />【含义】为待接入集群添加描述信息。         | 这是一个无状态工作负载，主要用来运行 Nginx 服务。 |

### 步骤 3  接入配置

完成上述步骤后，选择通过直接接入或者代理接入的接入方式接入集群。

- #### 直接接入

通过直接接入集群需要确保容器管理集群和待接入集群之间的网络通畅，前往待接入集群的任一 Master 节点，[读取 KubeConfig 文件](../../../kpanda/07UserGuide/Clusters/ClusterStatus.md)，复制到输入框中。

- #### 代理接入

.......

### 步骤 4  完成接入

确认所有参数输入完成后，点击`确定`按钮，完成集群接入。此时系统将自动跳转至集群列表界面，您可以在集群列表业看到您刚接入的集群。此时集群状态为 `接入中`。如集群状态出现异常，请查看具体异常信息，可参考[集群状态](../../../kpanda/07UserGuide/Clusters/ClusterStatus.md)。
