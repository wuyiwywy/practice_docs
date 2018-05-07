# HTKS部署回顾

* 作者: 吴益, 闫硕, 刘小林
* 本框架各部分具体版本如下：TiDB Docker:latest、Kubernetes 1.9.4、Tensorflow

- [TiDB部署](#TiDB部署)
- [Kubernetes xxx](#Kunbernetes xxx)
- [Tensorflow](#Tensorflow)


# TiDB部署

## 基本方法
1. 参考[参数说明](https://www.pingcap.com/docs-cn/op-guide/docker-deployment/),部署TiPD Server
1. 指定实例，部署TiDB Server
1. 在指定的三个实例上，部署TiKV Server

## 坑点记录
- **硬件环境**: 物理环境的内存及磁盘在不满足官方部署要求的前提条件下相关组件运行存在溢出的问题，
  最终导致组件镜像运行崩溃
- **频繁读写**: 当外部程序频繁通过TiDB对TiKV Server进行读写操作时，可能导致DB服务器出现奔溃的问题，
  需要对DB外部访问参数进行设置
- **PD相关事项**: 由于TiPD Server负责整个集群的内部调度，因此为了防止PD出现宕机的情况，应尽量部署
  两个以上的PD服务以保证调度服务的稳定性
  
# Kubernetes


# Tensorflow



