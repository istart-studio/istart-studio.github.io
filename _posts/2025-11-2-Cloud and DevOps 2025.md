---
layout: post
title: Cloud and DevOps 2025
date: 2025-11-2 00:00:00 +0800
description: 基于技术采用生命周期模型，系统梳理 2025 年云计算与 DevOps 领域的技术成熟度分布与演进趋势
img: # Add image post (optional)
tags: [devops,云原生,运维] # add tag
---

本文基于 Rogers 的技术采用生命周期模型（Technology Adoption Lifecycle），系统梳理 2025 年云计算与 DevOps 领域从「创新者（Innovators）」到「后期主流（Late Majority）」四个阶段的技术成熟度分布与演进趋势。

## Innovators（创新者阶段）

该阶段技术处于概念验证或早期实验阶段，主要由技术驱动型组织进行探索性应用，尚未形成成熟的工程实践与标准化方案。

| 技术                                 | 技术定义与核心价值                                                                    |
| ---------------------------------- | --------------------------------------------------------------------------- |
| **AI agents in cloud engineering** | 基于大语言模型（LLM）的智能代理系统，实现云基础设施运维与配置的自动化，包括 IaC 代码生成、告警自动修复、资源优化等能力。 |
| **MCP-based ops tooling**          | 基于模型上下文协议（Model Context Protocol）构建的运维工具链，通过标准化上下文接口实现 AI 代理在运维场景中的统一交互与管理。 |
| **Data observability**             | 数据可观测性技术，通过实时监控数据管道健康状态，自动检测数据质量异常、延迟波动、数据丢失等问题的系统性解决方案。         |
| **Quantum cloud computing**        | 量子计算与云服务融合架构，提供基于云平台的量子计算资源访问接口，使企业能够通过 API 调用量子处理能力。              |
| **Automation of governance**       | 云治理自动化框架，通过策略即代码（Policy as Code）实现企业级合规策略的自动化执行与审计，减少人工审查成本。      |
| **Low-code platforms**             | 低代码开发平台，通过可视化界面与配置化方式实现应用快速构建，降低非专业开发者的技术门槛，提升业务迭代效率。          |

---

## Early Adopters（早期采用者阶段）

该阶段技术已在部分技术领先企业实现生产级应用，具备相对成熟的工具链与最佳实践，但尚未达到行业级标准化与广泛采用。

| 技术                                               | 技术定义与核心价值                                                                        |
| ------------------------------------------------ | ------------------------------------------------------------------------------- |
| **Platform engineering teams**                   | 平台工程团队模式，通过构建和维护内部开发者平台（IDP），为开发团队提供标准化的基础设施抽象层，提升开发效率与交付一致性。      |
| **Cross-cloud / Cloud-native hybrid approaches** | 跨云与云原生混合架构，实现多云或混合云环境中的统一部署、监控、迁移与治理能力，支持工作负载在不同云平台间的无缝迁移。        |
| **DevEx Frameworks**                             | 开发者体验（Developer Experience）框架，通过工具链集成、流程优化与上下文管理，系统性提升开发者的生产力与工作满意度。    |
| **Cross-cloud uniform automation**               | 跨云统一自动化框架，基于声明式配置实现多云环境中的基础设施与应用的统一编排、部署与生命周期管理。                    |
| **Data Mesh**                                    | 数据网格架构范式，采用去中心化的数据治理模式，将数据作为产品由各业务团队自主管理，通过标准化接口实现数据资产的发现与消费。    |
| **Industry-aggregated incident analysis**        | 行业级事件聚合分析平台，通过跨组织的事件数据共享与模式识别，提升故障根因分析的准确性与响应效率。                    |
| **Policy as Code**                               | 策略即代码实践，将安全、合规与治理策略以代码形式定义，实现策略的版本管理、自动化执行与持续审计。                    |
| **WebAssembly (Wasm)**                           | WebAssembly 运行时技术，提供轻量级、安全隔离、高性能的二进制执行环境，支持在浏览器、边缘节点与云平台中运行。         |
| **Software secure supply chain**                 | 软件供应链安全体系，通过依赖扫描、签名验证、SBOM 生成与漏洞检测，保障软件从构建到部署全生命周期的安全性与完整性。        |
| **Sustainability accounting**                    | IT 可持续性核算体系，通过量化基础设施的能源消耗与碳排放，为绿色计算决策提供数据支撑，实现成本与环保的平衡优化。         |
| **AI/ML Ops**                                    | AI/ML 运维体系，扩展 MLOps 能力至 AI 应用全生命周期，涵盖模型训练、版本管理、持续部署、性能监控与 A/B 测试等环节。   |
| **Active-active Global DB Ops**                  | 全球多活数据库运维架构，实现跨地域的数据库集群同步与故障自动切换，保障全球业务的低延迟访问与高可用性。                |
| **Full-stack tracing**                           | 全栈分布式追踪技术，通过统一的追踪标准（如 OpenTelemetry）实现从用户请求到后端服务的端到端性能分析与问题定位。         |
| **ChatOps**                                      | 聊天式运维协作模式，将自动化脚本与运维工具集成到即时通讯平台（如 Slack、Teams），实现运维操作的协作化与可追溯性。      |
| **DataOps**                                      | 数据运维实践，将 DevOps 理念应用于数据工程领域，通过 CI/CD、版本控制与自动化测试提升数据管道的质量、可靠性与交付效率。   |
| **Documentation as Code**                        | 文档即代码实践，将技术文档纳入版本控制系统，通过 Markdown、AsciiDoc 等格式与自动化工具实现文档的持续集成与发布。      |

---

## Early Majority（早期主流阶段）

该阶段技术已在主流企业实现规模化应用，形成行业级最佳实践与标准化工具链，成为现代软件工程的基础能力。

| 技术                                     | 技术定义与核心价值                                                                      |
| -------------------------------------- | ----------------------------------------------------------------------------- |
| **Focus on developer experience**      | 开发者体验优化实践，通过统一工具链、减少上下文切换、优化反馈循环等方式，系统性提升开发者的生产力与工作满意度。          |
| **Service Mesh**                       | 服务网格架构，作为微服务通信的基础设施层，提供流量管理、安全策略、可观测性与故障恢复等能力（代表实现：Istio、Linkerd）。 |
| **eBPF**                               | 扩展伯克利数据包过滤器（Extended Berkeley Packet Filter），Linux 内核级可编程框架，用于构建高性能网络、安全与可观测性工具。 |
| **Continuous Testing**                 | 持续测试实践，将自动化测试集成到 CI/CD 流水线中，通过单元测试、集成测试、端到端测试等分层策略保障发布质量。            |
| **Chaos engineering practices**        | 混沌工程实践，通过在生产环境中可控地注入故障，验证系统的容错能力与恢复机制，提升系统韧性。                        |
| **Serverless databases**               | 无服务器数据库服务，提供按需自动扩缩容、零运维管理、按使用量计费的数据库解决方案，降低运维复杂度。                    |
| **Edge computing**                     | 边缘计算架构，在靠近数据源或用户的边缘节点部署计算资源，通过降低网络延迟与带宽消耗提升应用性能与用户体验。              |
| **Shift left on security / InfoSec**   | 安全左移实践，在软件开发生命周期的早期阶段（设计、编码、构建）引入安全测试、漏洞扫描与合规检查，降低安全风险与修复成本。    |
| **GitOps**                             | GitOps 运维模式，以 Git 仓库作为基础设施与应用的唯一事实源（Single Source of Truth），通过声明式配置与自动化同步实现集群状态管理。 |
| **CD for Mobile**                      | 移动端持续交付实践，通过自动化构建、测试、签名与分发流程，实现移动应用的快速迭代与灰度发布。                        |
| **Site Reliability Engineering (SRE)** | 站点可靠性工程，通过工程化方法平衡开发速度与系统可靠性，运用错误预算、SLO/SLI 等机制实现业务目标与稳定性目标的统一。      |
| **Blameless postmortems**              | 无责后检文化，在故障复盘过程中聚焦系统性问题与流程改进，而非个人责任追究，营造学习型组织氛围。                        |
| **Team Topologies**                    | 团队拓扑模型，基于 Conway 定律优化团队结构与交互模式，通过流式团队、平台团队、赋能团队等模式提升组织效能。              |
| **Measuring performance (Accelerate)** | 性能度量框架，基于《Accelerate》提出的四个关键指标（部署频率、变更前置时间、变更失败率、服务恢复时间）评估工程效能。      |
| **DORA metrics**                       | DORA 指标体系，由 DevOps Research and Assessment 项目定义的标准化 DevOps 成熟度评估指标，用于量化工程能力。    |

---

## Late Majority（后期主流阶段）

该阶段技术已成为行业标准与基础设施，被绝大多数企业采用，形成成熟的生态系统与广泛的技术社区支持。

| 技术                                         | 技术定义与核心价值                                                                          |
| ------------------------------------------ | --------------------------------------------------------------------------------- |
| **Continuous Delivery (CD)**               | 持续交付实践，通过自动化构建、测试、部署流程，确保软件始终处于可发布状态，实现快速、安全、可靠的软件交付。                |
| **FinOps**                                 | 云财务管理实践，通过成本可见性、资源优化与预算控制，实现云支出的透明化管理，平衡业务性能需求与成本效益。                |
| **(Enterprise) DevOps toolchain**          | 企业级 DevOps 工具链，集成 CI/CD、IaC、监控、安全等能力，提供端到端的软件交付与运维支撑（代表工具：Jenkins、GitLab、ArgoCD）。 |
| **Observability**                          | 可观测性体系，通过日志（Logs）、指标（Metrics）、追踪（Traces）三大支柱，实现对分布式系统的全面监控与问题诊断。          |
| **CI best practices**                      | 持续集成最佳实践，包括代码质量检查、自动化测试、快速反馈、构建优化等标准化流程，保障代码集成的质量与效率。                |
| **FaaS / BaaS**                            | 函数即服务（Function as a Service）与后端即服务（Backend as a Service），提供无服务器计算与托管服务能力（代表：AWS Lambda、Firebase）。 |
| **Monitoring and logging**                 | 系统监控与日志管理能力，通过实时指标采集、日志收集与分析，实现对应用与基础设施运行状态的持续观察与告警。                |
| **Centralized log aggregation**            | 集中化日志聚合平台，统一收集、存储、索引与分析来自多源的应用日志，提供高效的日志检索与问题排查能力（代表：ELK Stack、Datadog）。 |
| **Infrastructure as Code (IaC)**           | 基础设施即代码实践，通过声明式或命令式代码定义基础设施配置，实现基础设施的版本管理、自动化部署与一致性保障。                |
| **Containers**                             | 容器化技术，通过操作系统级虚拟化实现应用与运行环境的标准化封装，提升应用的可移植性与部署一致性（代表：Docker）。           |
| **Container orchestration**                | 容器编排系统，自动化管理大规模容器集群的生命周期，包括调度、扩缩容、服务发现、负载均衡等能力（代表：Kubernetes）。          |
| **Software-Defined Networks (SDN)**        | 软件定义网络技术，通过集中式控制平面与数据平面分离，实现网络配置的灵活管理与自动化编排，提升网络运维效率。                |
| **Continuous integration tooling**         | 持续集成工具链，提供代码构建、测试执行、质量检查等自动化能力，支撑快速迭代的开发流程（代表：Jenkins、CircleCI、GitHub Actions）。 |
| **Self-service platforms**                 | 自助式开发者平台，为开发团队提供标准化的基础设施与工具访问接口，实现部署、监控、调试等操作的自主化，减少运维依赖。            |
| **DevOps Toolchain**                       | DevOps 端到端工具生态，涵盖从代码提交到生产部署的全流程工具链，实现开发与运维的深度集成与自动化。                    |
| **General DevOps**                         | DevOps 通用实践，包括文化转型、流程优化、工具集成等综合实践，已成为现代软件工程的标准方法论。                        |
| **Feature Flags & Blue/Green Deployments** | 功能开关与蓝绿部署策略，通过运行时配置控制功能发布，结合双环境切换实现零停机部署与快速回滚，降低发布风险。              |

# 技术栈

以下章节列出各阶段技术对应的代表性工具与技术栈，供技术选型参考。

---

## Innovators（创新者阶段）

| 技术                                 | 代表性工具与技术栈                                                                    |
| ---------------------------------- | --------------------------------------------------------------------------- |
| **AI agents in cloud engineering** | OpenAI API、LangChain、AutoGPT、Azure AI Agents、Kubiya.ai、Cortex.dev            |
| **MCP-based ops tooling**          | Model Context Protocol (OpenAI)、LangGraph、OpenDevin、Cognosys                 |
| **Data observability**             | Monte Carlo、Databand、Bigeye、Soda Core、OpenLineage、Apache Superset            |
| **Quantum cloud computing**        | IBM Qiskit、Amazon Braket、Azure Quantum、Google Cirq                           |
| **Automation of governance**       | Open Policy Agent (OPA)、HashiCorp Sentinel、AWS Control Tower、Terraform Cloud |
| **Low-code platforms**             | OutSystems、Mendix、Retool、PowerApps、Appsmith、Budibase                         |

---

## Early Adopters（早期采用者阶段）

| 技术                                        | 代表性工具与技术栈                                                            |
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

| 技术                                     | 代表性工具与技术栈                                                                                             |
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

| 技术                                         | 代表性工具与技术栈                                                         |
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
