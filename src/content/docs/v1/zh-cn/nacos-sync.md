---
title: NacosSync 介绍
keywords: [NacosSync,介绍]
description: NacosSync 介绍
---

# NacosSync 介绍

## 介绍
* NacosSync是一个支持多种注册中心的同步组件,基于Spring boot开发框架,数据层采用Spring Data JPA,遵循了标准的JPA访问规范,支持多种数据源存储,默认使用Hibernate实现,更加方便的支持表的自动创建更新
* 使用了高效的事件异步驱动模型, 支持多种自定义事件,使得同步任务处理的延时控制在3s,8C16G的单机能够支持6K的同步任务
* NacosSync除了单机部署,也提供了高可用的集群部署模式,NacosSync是无状态设计,将任务等状态数据迁移到了数据库,使得集群扩展非常方便
* 抽象出了Sync组件核心接口,通过注解对同步类型进行区分,使得开发者可以很容易的根据自己需求,去扩展不同注册中心,目前已支持的同步类型:
  * Nacos数据同步到Nacos
  * Zookeeper数据同步到Nacos
  * Nacos数据同步到Zookeeper
  * Eureka数据同步到Nacos
  * Consul数据同步到Nacos
<a name="d384971e"></a>
## 系统模块架构:
![image.png](https://img.alicdn.com/tfs/TB12VPaJVzqK1RjSZSgXXcpAVXa-886-752.png)<br />控制台<br />提供了精简Web操作控制台,支持国际化:<br />
<a name="b3408d06"></a>
### 同步任务管理页面
![](https://img.alicdn.com/tfs/TB1eSYyJ5LaK1RjSZFxXXamPFXa-2866-1064.png)
<a name="091bc34b"></a>
### 注册中心管理页面
<a name="53fdb015"></a>
## ![image.png](https://img.alicdn.com/tfs/TB1e_rdJ7voK1RjSZFNXXcxMVXa-2876-1124.png)
<a name="f6a633db"></a>
## 使用场景:
* 多个网络互通的Region之间服务共享,打破Region之间的服务调用限制

![image.png](https://img.alicdn.com/tfs/TB1Mo6yJ4jaK1RjSZKzXXXVwXXa-1136-798.png)

* 双向同步功能,支持Dubbo+Zookeeper服务平滑迁移到Dubbo+Nacos,享受Nacos更加优质的服务

![image.png](https://img.alicdn.com/tfs/TB1Dza8J9zqK1RjSZPxXXc4tVXa-1728-838.png)