# 安全治理

Istio 提供了一种授权机制和两种认证方式，分别为授权策略、请求身份认证和对等身份认证三种资源，
在服务网格中提供了这三种安全治理资源的创建、管理功能，用户可以通过表单和YAML编写两种方式创建、编辑资源文件。
并可以针对网格全局、命名空间、工作负载三个层面创建规则，当资源创建成功后，Istiod 将转换为配置分发至边车代理执行。

![安全治理](../../images/security.png)