# Anchor Projects Repo Wiki — 技术栈学习索引

> 本Wiki为9个锚定项目提供统一的技术栈映射和学习路径，方便快速定位需要深入的方向。

---

## 项目速查表

| 项目 | 一句话定位 | 核心技术栈 | 学习难度 | 面试价值 |
|------|-----------|-----------|---------|---------|
| Dify | 生产级LLM应用平台 | Python, FastAPI, PostgreSQL, Redis, Docker, K8s | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| LangChain | LLM应用开发框架 | Python, LLM API, Vector DB, Chain/Agent | ⭐⭐ | ⭐⭐⭐⭐⭐ |
| LlamaIndex | 数据索引与RAG框架 | Python, Vector DB, Document Loader | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| vn.py | 量化交易平台 | Python, MongoDB, Redis, WebSocket, PyQt | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| Flowise | 可视化LLM工作流 | TypeScript, Node.js, React, LangChain.js | ⭐⭐ | ⭐⭐⭐ |
| Open Interpreter | 本地代码执行Agent | Python, LLM API, 代码沙箱 | ⭐⭐⭐ | ⭐⭐⭐ |
| Saleor | Headless电商平台 | Python, GraphQL, Django, React, PostgreSQL | ⭐⭐⭐ | ⭐⭐⭐ |
| Apache Airflow | 数据工作流调度 | Python, DAG, Docker/K8s | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Prefect | 现代数据工作流 | Python, DAG, Docker/K8s | ⭐⭐⭐ | ⭐⭐⭐ |

---

## 按技术栈分类学习

### Python后端

| 技术 | 涉及项目 | 学习重点 | 推荐顺序 |
|------|---------|---------|---------|
| FastAPI | Dify | 异步API、依赖注入、中间件 | 1 |
| Django | Saleor, Label Studio | ORM、Admin、REST Framework | 2 |
| Flask/Express | Flowise | 轻量级API | 3 |

### 数据库

| 技术 | 涉及项目 | 学习重点 |
|------|---------|---------|
| PostgreSQL | Dify, Saleor, Label Studio, Airflow | JSONB、全文检索、分区表 |
| Redis | Dify, vn.py | 缓存、消息队列、会话存储 |
| MongoDB | vn.py | 文档存储、聚合管道 |
| Chroma/Pinecone | LangChain, LlamaIndex | 向量数据库、相似度搜索 |

### 前端

| 技术 | 涉及项目 | 学习重点 |
|------|---------|---------|
| React | Flowise, Saleor, Label Studio | 组件化、状态管理、Hooks |
| TypeScript | Flowise | 类型系统、接口设计 |
| Next.js | Saleor | SSR、API Routes |

### AI/ML核心

| 技术 | 涉及项目 | 学习重点 |
|------|---------|---------|
| RAG | LangChain, LlamaIndex, Dify | 检索增强生成、向量索引、Chunk策略 |
| Agent | LangChain, Dify, Open Interpreter | 工具调用、多步推理、ReAct模式 |
| LLM编排 | Dify, Flowise | 多模型切换、Prompt管理、流式输出 |
| 代码执行沙箱 | Open Interpreter | 安全执行、结果捕获、环境隔离 |

### DevOps/MLOps

| 技术 | 涉及项目 | 学习重点 |
|------|---------|---------|
| Docker Compose | Dify, Saleor, Airflow | 多容器编排、网络配置、卷管理 |
| Kubernetes | Dify, Airflow | 容器编排、Service、Deployment |
| CI/CD | 所有项目 | GitHub Actions、自动化测试 |
| 工作流调度 | Airflow, Prefect | DAG定义、任务依赖、监控告警 |

### 领域特定

| 技术 | 涉及项目 | 学习重点 |
|------|---------|---------|
| GraphQL | Saleor | Schema设计、Resolver、Subscription |
| 事件驱动架构 | vn.py | 事件引擎、消息总线、策略生命周期 |
| WebSocket | vn.py | 实时数据推送、连接管理 |
| 量化策略 | vn.py | CTA策略、回测框架、风控 |

---

## 学习路径推荐

### 路径A: AI应用工程师（Prof DS方向）

```
Week 1-2: LangChain官方教程 → 理解Chain/Agent/Tool概念
Week 3-4: LlamaIndex文档 → 掌握数据索引和RAG
Week 5-6: Dify源码拆解 → 理解生产级架构
Week 7-8: Open Interpreter → 理解代码执行Agent
Week 9-12: 实战项目 → 金融研报Agent + 地产估值助手
```

### 路径B: AI技术负责人（Lead方向）

```
Week 1-2: Dify部署 + 架构理解 → 系统思维
Week 3-4: Airflow/Prefect → MLOps基础设施
Week 5-6: Saleor Plugin开发 → 工程化能力
Week 7-8: Flowise → 降低技术门槛的产品思维
Week 9-12: 多租户SaaS原型 → 架构设计 + 团队管理
```

### 路径C: 量化/金融AI方向

```
Week 1-3: vn.py架构拆解 → 事件驱动 + 策略引擎
Week 4-6: LangChain金融Agent → NLP + 金融数据
Week 7-9: 情绪因子策略 → NLP新闻分析 + 交易信号
Week 10-12: 完整交易系统 → 回测 + 风控 + Dashboard
```

---

## 关键源码入口

| 项目 | 核心目录 | 关键文件 |
|------|---------|---------|
| Dify | `api/`, `web/` | `api/core/workflow/`, `api/core/rag/` |
| LangChain | `libs/langchain/` | `libs/langchain/core/`, `libs/langchain/chains/` |
| LlamaIndex | `llama-index-core/` | `llama-index-core/llama_index/core/indices/` |
| vn.py | `vnpy/` | `vnpy/trader/engine.py`, `vnpy/trader/gateway/` |
| Flowise | `packages/` | `packages/server/`, `packages/components/` |
| Open Interpreter | `interpreter/` | `interpreter/core/`, `interpreter/terminal_interface/` |
| Saleor | `saleor/` | `saleor/graphql/`, `saleor/plugins/` |
| Airflow | `airflow/` | `airflow/models/`, `airflow/operators/` |
| Prefect | `src/prefect/` | `src/prefect/flows/`, `src/prefect/tasks/` |

---

## 面试高频考点映射

| 面试问题 | 对应项目 | 回答要点 |
|---------|---------|---------|
| "你如何设计一个RAG系统？" | LangChain + LlamaIndex | Chunk策略、向量索引、重排序、引用标注 |
| "如何保证LLM输出的可靠性？" | Dify + LangChain | 引用来源、事实核查、幻觉检测 |
| "你如何管理AI系统的成本？" | Dify | Token计量、模型路由、缓存策略 |
| "如何设计一个可扩展的AI平台？" | Dify + Saleor | 多租户、Plugin系统、API Gateway |
| "你如何处理实时数据流？" | vn.py | 事件驱动、WebSocket、消息队列 |
| "如何编排复杂的数据管道？" | Airflow + Prefect | DAG设计、任务依赖、失败重试 |
| "如何让非技术人员使用AI？" | Flowise + Dify | 可视化搭建、低代码、拖拽式Workflow |

---

*本Wiki随项目进展持续更新。最后更新: 2026-07-06*
