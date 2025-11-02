---
layout: post
title: Cloud and DevOps 2025
date: 2025-11-2 00:00:00 +0800
description:  # Add post description (optional)
img: # Add image post (optional)
tags: [devops,云原生,运维] # add tag
---

展示了云计算与 DevOps 领域从「创新者（Innovators）」到「后期主流（Late Majority）」的技术趋势演进。

## Innovators（创新者阶段）

这些技术仍处于探索或实验阶段，通常由行业前沿公司率先尝试。

| 技术                                 | 简介                                                            |
| ---------------------------------- | ------------------------------------------------------------- |
| **AI agents in cloud engineering** | 使用 AI 智能体自动化云运维与系统配置，例如利用 LLM 生成 IaC（基础设施即代码）或自动修复告警。         |
| **MCP-based ops tooling**          | 基于模型控制协议（Model Context Protocol）的运维工具，通过统一上下文管理 AI 代理在运维中的交互。 |
| **Data observability**             | 提供数据健康可视化监控的技术，用于发现数据质量、延迟、丢失等问题。                             |
| **Quantum cloud computing**        | 结合量子计算和云服务，使用户通过云访问量子处理资源。                                    |
| **Automation of governance**       | 自动化企业云治理与合规策略执行，减少人工审查。                                       |
| **Low-code platforms**             | 通过可视化或配置方式快速构建应用的开发平台，降低开发门槛。                                 |

---

##  Early Adopters（早期采用者阶段）

这些技术已在部分领先企业应用，但尚未形成行业普及。

| 技术                                               | 简介                                        |
| ------------------------------------------------ | ----------------------------------------- |
| **Platform engineering teams**                   | 建立专门团队创建和维护开发者平台，提高开发效率与一致性。              |
| **Cross-cloud / Cloud-native hybrid approaches** | 实现多云或混合云环境中一致的部署、监控与迁移能力。                 |
| **DevEx Frameworks**                             | 专注于改善开发者体验（Developer Experience）的框架与流程体系。 |
| **Cross-cloud uniform automation**               | 通过自动化脚本在多云间统一操作与部署。                       |
| **Data Mesh**                                    | 一种去中心化的数据架构理念，让不同团队各自管理和发布“数据产品”。         |
| **Industry-aggregated incident analysis**        | 跨行业事件聚合分析，帮助改进故障根因分析与响应机制。                |
| **Policy as Code**                               | 用代码定义治理与安全策略，实现自动化合规。                     |
| **WebAssembly (Wasm)**                           | 一种轻量、安全、高性能的二进制运行格式，可在浏览器或云端运行。           |
| **Software secure supply chain**                 | 保障软件供应链安全的体系，防止依赖组件被攻击或篡改。                |
| **Sustainability accounting**                    | 用于评估 IT 基础设施能耗和碳排放的体系，助力绿色计算。             |
| **AI/ML Ops**                                    | 机器学习模型的持续集成、交付与监控体系（MLOps 的扩展版）。          |
| **Active-active Global DB Ops**                  | 全球分布式数据库的多活部署与容灾运维。                       |
| **Full-stack tracing**                           | 对全栈应用进行端到端性能追踪（如分布式追踪系统）。                 |
| **ChatOps**                                      | 通过聊天平台（如 Slack）集成自动化脚本执行和运维命令。            |
| **DataOps**                                      | 数据工程的 DevOps 化，提高数据流的质量与交付效率。             |
| **Documentation as Code**                        | 将文档版本管理与代码同源化，通过自动化工具生成与发布。               |

---

## Early Majority（早期主流阶段）

这些技术已在主流企业中落地，被广泛采用。

| 技术                                     | 简介                                 |
| -------------------------------------- | ---------------------------------- |
| **Focus on developer experience**      | 企业聚焦开发者体验优化，如统一工具链、减少上下文切换。        |
| **Service Mesh**                       | 用于微服务间通信治理的基础设施层（如 Istio、Linkerd）。 |
| **eBPF**                               | 一种 Linux 内核技术，用于高性能网络、安全与可观测性工具。   |
| **Continuous Testing**                 | 在持续集成流水线中自动化测试流程，提升发布质量。           |
| **Chaos engineering practices**        | 混沌工程，用于主动注入故障以测试系统韧性。              |
| **Serverless databases**               | 无服务器化数据库，按需扩缩容、自动管理。               |
| **Edge computing**                     | 在靠近数据源的边缘节点运行计算，减少延迟。              |
| **Shift left on security / InfoSec**   | 在开发早期引入安全测试与合规扫描。                  |
| **GitOps**                             | 用 Git 仓库作为部署配置的唯一事实源，通过自动化同步集群状态。  |
| **CD for Mobile**                      | 持续交付在移动端的实现，包括版本控制与灰度发布。           |
| **Site Reliability Engineering (SRE)** | 平衡开发速度与系统可靠性的工程文化与实践。              |
| **Blameless postmortems**              | “无责后检”文化，通过复盘故障原因而非归责。             |
| **Team Topologies**                    | 团队拓扑模型，用于优化团队结构与交互方式。              |
| **Measuring performance (Accelerate)** | 来自《Accelerate》书籍的四个关键指标（部署频率等）。    |
| **DORA metrics**                       | 用于衡量 DevOps 成熟度的标准化指标体系。           |

---

## Late Majority（后期主流阶段）

这些技术已成为行业标准，被普遍采纳。

| 技术                                         | 简介                                          |
| ------------------------------------------ | ------------------------------------------- |
| **Continuous Delivery (CD)**               | 自动化发布流程，确保代码可随时安全上线。                        |
| **FinOps**                                 | 云成本管理与优化实践，平衡性能与支出。                         |
| **(Enterprise) DevOps toolchain**          | 企业级 DevOps 工具链，如 Jenkins、GitLab、ArgoCD 等。   |
| **Observability**                          | 可观测性体系，整合日志、指标、追踪来监控系统状态。                   |
| **CI best practices**                      | 持续集成的标准化最佳实践。                               |
| **FaaS / BaaS**                            | 函数即服务 / 后端即服务，如 AWS Lambda、Firebase。        |
| **Monitoring and logging**                 | 系统监控与日志收集的核心能力。                             |
| **Centralized log aggregation**            | 集中化日志聚合与分析平台，如 ELK、Datadog。                 |
| **Infrastructure as Code (IaC)**           | 用代码定义基础设施，实现自动化部署。                          |
| **Containers**                             | 容器化技术（如 Docker）标准化了应用部署方式。                  |
| **Container orchestration**                | 容器编排系统，如 Kubernetes，用于管理大规模容器集群。            |
| **Software-Defined Networks (SDN)**        | 通过软件控制网络配置，实现灵活的网络管理。                       |
| **Continuous integration tooling**         | 持续集成工具链（如 Jenkins、CircleCI、GitHub Actions）。 |
| **Self-service platforms**                 | 自助式平台，使开发团队独立完成部署与监控。                       |
| **DevOps Toolchain**                       | DevOps 的端到端工具生态体系。                          |
| **General DevOps**                         | DevOps 文化与流程的普遍落地实践。                        |
| **Feature Flags & Blue/Green Deployments** | 功能开关与蓝绿部署，用于安全发布新版本。                        |

# 技术栈

---

## Innovators（创新者阶段）

| 技术                                 | 对应技术栈与代表性工具                                                                  |
| ---------------------------------- | ---------------------------------------------------------------------------- |
| **AI agents in cloud engineering** | OpenAI API、LangChain、AutoGPT、Azure AI Agents、Kubiya.ai、Cortex.dev            |
| **MCP-based ops tooling**          | Model Context Protocol (OpenAI)、LangGraph、OpenDevin、Cognosys                 |
| **Data observability**             | Monte Carlo、Databand、Bigeye、Soda Core、OpenLineage、Apache Superset            |
| **Quantum cloud computing**        | IBM Qiskit、Amazon Braket、Azure Quantum、Google Cirq                           |
| **Automation of governance**       | Open Policy Agent (OPA)、HashiCorp Sentinel、AWS Control Tower、Terraform Cloud |
| **Low-code platforms**             | OutSystems、Mendix、Retool、PowerApps、Appsmith、Budibase                         |

---

## Early Adopters（早期采用者阶段）

| 技术                                        | 对应技术栈与代表性工具                                                            |
| ----------------------------------------- | ---------------------------------------------------------------------- |
| **Platform engineering teams**            | Backstage、Humanitec、Port.io、KrakenD、Internal Developer Portals         |
| **Cross-cloud / Hybrid approaches**       | Anthos（Google）、Azure Arc、AWS Outposts、HashiCorp Terraform、Crossplane   |
| **DevEx Frameworks**                      | Backstage、Nx Monorepo、TurboRepo、GitHub Copilot、JetBrains AI            |
| **Cross-cloud uniform automation**        | Terraform、Pulumi、Ansible、Spacelift、Cloudify                            |
| **Data Mesh**                             | Databricks Delta Lake、Snowflake Data Sharing、Apache Kafka、dbt、DataHub  |
| **Industry-aggregated incident analysis** | PagerDuty、Honeycomb、Datadog Incident、Blameless、Jeli.io                 |
| **Policy as Code**                        | OPA（Open Policy Agent）、Conftest、Terraform Sentinel、Kyverno             |
| **WebAssembly (Wasm)**                    | Wasmtime、Spin、Suborbital、WASI、Fermyon Cloud、Cloudflare Workers         |
| **Software secure supply chain**          | Sigstore、SLSA、in-toto、Cosign、Syft/Grype、GitHub Dependabot              |
| **Sustainability accounting**             | Cloud Carbon Footprint、AWS Carbon Tracker、Google Cloud Footprint API   |
| **AI/ML Ops**                             | Kubeflow、MLflow、Weights & Biases、SageMaker、Vertex AI、Airflow           |
| **Active-active Global DB Ops**           | CockroachDB、YugabyteDB、Aurora Global、Spanner、PlanetScale               |
| **Full-stack tracing**                    | OpenTelemetry、Jaeger、Tempo、Honeycomb、New Relic                         |
| **ChatOps**                               | Slack + BotKube、Mattermost、Microsoft Teams Bots、GitHub Actions ChatOps |
| **DataOps**                               | Airbyte、dbt、Dagster、Prefect、Great Expectations                         |
| **Documentation as Code**                 | MkDocs、Docusaurus、GitBook CLI、Sphinx、Docsify                           |

---

## Early Majority（早期主流阶段）

| 技术                                     | 对应技术栈与代表性工具                                                                                             |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Developer Experience (DevEx)**       | Backstage、VS Code Extensions、Nx/Turborepo、GitHub Actions、Vercel                                         |
| **Service Mesh**                       | Istio、Linkerd、Consul Connect、Kuma、AWS App Mesh                                                          |
| **eBPF**                               | Cilium、Pixie、BPFTrace、Falco、Tetragon                                                                    |
| **Continuous Testing**                 | GitHub Actions + Playwright、Cypress、JUnit5、Testcontainers、Allure                                        |
| **Chaos Engineering**                  | Gremlin、LitmusChaos、ChaosMesh、Steadybit                                                                 |
| **Serverless Databases**               | Aurora Serverless、Neon、PlanetScale、FaunaDB、Supabase                                                     |
| **Edge Computing**                     | Cloudflare Workers、AWS Lambda@Edge、Vercel Edge Functions、Fastly Compute@Edge                            |
| **Shift-left on Security**             | Snyk、Checkov、Trivy、GitHub Advanced Security、OWASP ZAP                                                   |
| **GitOps**                             | ArgoCD、FluxCD、Weave GitOps、Spacelift、Jenkins X                                                          |
| **CD for Mobile**                      | Bitrise、AppCenter、Fastlane、GitHub Actions Mobile CI/CD                                                  |
| **SRE（Site Reliability Engineering）**  | Prometheus、Grafana、Alertmanager、SLO Generator、Nobl9                                                     |
| **Blameless Postmortems**              | Atlassian Opsgenie、Blameless、Rootly、Incident.io                                                         |
| **Team Topologies**                    | Notion/Confluence + Architecture Decision Records (ADR)、Backstage                                       |
| **Measuring Performance (Accelerate)** | DORA Metrics、LinearB、Pluralsight Flow、Jellyfish、DevLake                                                 |
| **DORA Metrics**                       | Four Key Metrics（Deployment Frequency, Lead Time, MTTR, Change Failure Rate）—由 DevLake、Grafana Tempo 支持 |

---

## Late Majority（后期主流阶段）

| 技术                                         | 对应技术栈与代表性工具                                                         |
| ------------------------------------------ | ------------------------------------------------------------------- |
| **Continuous Delivery (CD)**               | Jenkins、GitLab CI/CD、GitHub Actions、ArgoCD、Spinnaker                |
| **FinOps**                                 | Apptio Cloudability、Kubecost、Spot.io、AWS Cost Explorer、CloudZero    |
| **Enterprise DevOps Toolchain**            | Atlassian Stack（Jira, Bitbucket, Bamboo）、GitLab、Azure DevOps        |
| **Observability**                          | Prometheus、Grafana、Datadog、New Relic、OpenTelemetry、Splunk           |
| **CI Best Practices**                      | Jenkins、GitHub Actions、CircleCI、GitLab CI、Bazel CI                  |
| **FaaS / BaaS**                            | AWS Lambda、Azure Functions、Google Cloud Functions、Firebase、Supabase |
| **Monitoring & Logging**                   | Prometheus、Grafana Loki、ELK（Elastic, Logstash, Kibana）、Fluent Bit   |
| **Centralized Log Aggregation**            | ELK、Graylog、Datadog Logs、New Relic Logs                             |
| **Infrastructure as Code (IaC)**           | Terraform、Pulumi、Ansible、Chef、CloudFormation                        |
| **Containers**                             | Docker、Podman、Buildah                                               |
| **Container Orchestration**                | Kubernetes、K3s、EKS、GKE、AKS                                          |
| **Software-Defined Networks (SDN)**        | Calico、Cilium、Open vSwitch、Flannel                                  |
| **Continuous Integration Tooling**         | Jenkins、GitHub Actions、GitLab CI、CircleCI                           |
| **Self-service Platforms**                 | Backstage、Humanitec、Port.io、Harness                                 |
| **DevOps Toolchain**                       | GitHub + Terraform + ArgoCD + Prometheus + Grafana                  |
| **General DevOps**                         | Agile + CI/CD + IaC + Monitoring 标准实践                               |
| **Feature Flags & Blue/Green Deployments** | LaunchDarkly、Unleash、Split.io、Argo Rollouts、Spinnaker               |

---
