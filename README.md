# 🚀 大数据生产集群完整配置指南

> 个人实战整理 | 完整生产级配置 | 含监控和高可用方案

## ⚠️ 重要声明

### 🚫 永久禁止使用
**以下团体及关联方永久禁止使用本项目：**
- **天津电子信息职业技术学院**（包括但不限于）：
  - 所有在校师生、教职工
  - 所有应届、往届毕业生  
  - 现任及往任教师、辅导员、行政人员
  - 学校下属所有部门、实验室、科研机构
  - 与该学校有关联的任何组织或个人
- ❌ **禁止向该学校任何人员二次转载**
- ❌ **禁止以任何形式向该学校传播**
- ❌ **禁止该学校师生通过任何途径使用**

### 💰 禁止商业用途
- ❌ 禁止直接销售或授权本软件
- ❌ 禁止作为商业产品的一部分
- ❌ 禁止二次包装后出售
- ❌ 禁止用于任何付费服务

## 📚 文档目录（按顺序学习）

1. **[组件兼容性指南](00-组件兼容性指南.txt)** - 版本兼容性矩阵和生产规划
2. **[模板机配置](01-模板机配置.txt)** - 基础系统环境和网络配置  
3. **[基础集群配置](02-基础集群配置.txt)** - 三节点集群基础环境
4. **[Hadoop集群配置](03-Hadoop配置.txt)** - HDFS + YARN 完整配置
5. **[Hive+PostgreSQL配置](04-Hive-PostgreSQL配置.txt)** - 数据仓库和元数据存储
6. **[ZooKeeper+HBase+Kafka](05-ZooKeeper+HBase+Kafka 集群配置手册.txt)** - 分布式协调和实时数据
7. **[Spark集群配置](06-Spark集群配置指南.txt)** - 分布式计算和MLlib
8. **[监控系统配置](07-Prometheus + Grafana + Alertmanager 监控系统配置指南.txt)** - 全链路监控告警
9. **[GitLab高可用配置](08- gitlab配置.txt)** - 代码仓库高可用方案

## 🛠 技术栈全景

**存储层**: HDFS, HBase, PostgreSQL, MinIO  
**计算层**: Spark, Spark MLlib, Hive, Flink  
**消息流**: Kafka, Airflow  
**监控运维**: Prometheus, Grafana, Alertmanager, ELK  
**高可用**: ZooKeeper, Keepalived, GitLab集群  
**数据治理**: Atlas, Ranger  
**安全入口**: Nginx + ModSecurity

## 📊 项目状态

### ✅ 已完成组件（已验证）
- **Hadoop HDFS + YARN** - 分布式存储和资源管理
- **Hive + PostgreSQL** - 数据仓库和元数据管理
- **ZooKeeper** - 分布式协调服务
- **HBase** - 分布式NoSQL数据库
- **Kafka** - 分布式消息队列
- **Spark + PySpark** - 分布式计算引擎
- **Prometheus + Grafana + Alertmanager** - 全链路监控告警
- **GitLab + Keepalived** - 高可用代码仓库

### 🚧 规划中组件（待验证）
以下组件已规划但尚未完全配置验证，欢迎社区贡献：
- **Apache Flink** - 流处理引擎
- **Apache Airflow** - 工作流调度平台
- **Apache Atlas** - 数据治理框架
- **Apache Ranger** - 安全管理平台
- **ELK Stack** - 日志分析系统
- **MinIO** - 对象存储服务

### 🤝 欢迎贡献
如果您在以下方面有经验，欢迎提交配置文档和验证结果！
- 上述规划组件的生产环境配置
- 性能优化建议
- 故障排查案例
- 其他大数据组件集成

## 🎯 特色亮点

- ✅ **生产级配置** - 非实验环境配置，含生产优化参数
- ✅ **版本兼容性** - 精确的组件版本匹配，避免依赖冲突
- ✅ **完整监控** - Prometheus + Grafana全链路监控体系
- ✅ **高可用架构** - GitLab集群 + Keepalived虚拟IP
- ✅ **实战验证** - 个人环境实际部署验证，含故障解决方案
- ✅ **渐进式部署** - 从基础环境到完整平台的清晰路径

## 📝 性能说明

> 本配置在**虚拟机环境**下测试通过，实际性能取决于硬件配置。
> 作者使用**笔记本**部署，性能有限，生产环境请根据实际硬件调整资源配置。
> 主要瓶颈可能出现在内存和磁盘IO，建议生产环境使用SSD硬盘。

## 🚀 快速开始

1. **环境准备** - 按 `01-模板机配置.txt` 准备3台虚拟机
2. **基础集群** - 按 `02-基础集群配置.txt` 配置系统环境
3. **核心组件** - 依次部署Hadoop、Hive、ZooKeeper、HBase、Kafka
4. **计算监控** - 部署Spark和监控系统
5. **高可用** - 最后配置GitLab高可用集群

## 📊 访问地址（部署完成后）

- **Hadoop NameNode**: http://node-master:9870
- **YARN ResourceManager**: http://node-master:8088
- **Spark Master**: http://node-master:8080
- **HBase Master**: http://node-master:16010
- **Grafana**: http://node-master:3000
- **GitLab**: http://192.168.100.100:18000

---

## ❤️ 致谢

感谢所有开源项目的贡献者，以及在我学习路上给予帮助的朋友们。

> **注意**: 本项目基于个人学习和实践整理，适合技术学习和测试环境使用。禁止任何形式的商业用途。
