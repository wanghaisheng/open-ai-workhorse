# OpenAI Workhorse 项目总纲

**版本：** 1.5  
**日期：** 2026-05-12  
**状态：** Single Source of Truth（SSOT）  

---

## 1. 项目愿景

**OpenAI Workhorse**（简称 Workhorse）的使命是：

> **让 AI 成为组织中真正的第一等劳动力（First-class AI Workforce）**。

我们不再把 AI 当成一次性提示词工具，而是将其构建为**可招募、可分配、可考核、可进化、可长期积累**的组织资产。让每一位开发者、设计师、产品经理都能像管理人类团队一样，轻松拥有并管理一支强大、稳定、持续进化的 AI 团队。

### 核心口号

**You own the product. Workhorse owns the team.**

**口号解释**：

- **You own the product**：你专注于产品愿景、创新和最终交付成果。
- **Workhorse owns the team**：Workhorse（工作马）负责组建、管理、优化整个 AI 团队。

**“Workhorse”** 是对 AI 团队的**亲切戏称**，像一匹勤奋、可靠、能吃苦耐劳的“工作马”（老黄牛），可以 7×24 小时不疲倦地工作、承担繁重任务、持续积累经验。用户无需操心团队组建、人员调度、知识管理等繁琐事务，只需提出需求，Workhorse 就会为你组建并管理一支专业的 AI 团队。

---

## 2. 核心理念：人类职业体系向 AI 的迁移

本项目将人类劳动力市场的语义结构（**Occupation → Position → Role → Task → Skill**）系统性迁移到 AI 体系，构建一套**AI 能力与任务之间的标准语言（Capability Interface）**。

**核心意义**：
- 把“抽象的 AI 能力”映射到现实世界的“工作结构”
- 让 AI Agent 能够像员工一样被定义、分配、评估和协作
- 实现 Human-AI 统一编排与任务分配
- 最终形成 **AI Capability Graph**（AI 能力图谱），驱动 Agent 选择、工作流自动化和能力基准测试

---

## 3. 核心架构：RAMS

**RAMS (Role-Actor-Market System)** 是 OpenAI Workhorse 的**组织操作系统**和**核心实现框架**。

**关系定位**：
- **OpenAI Workhorse = What**（产品愿景与哲学）
- **RAMS = How**（组织管理方法论与具体架构实现）

---

## 4. 设计哲学

RAMS 的根本原则是：

**将组织资产（Role、Skill、Soul、Memory）与执行资源（Actor）彻底解耦**，通过 Orchestrator + 量化机制 + 双轨进化，把人类团队中大量协调性、执行性、记忆性、规模化问题转化为**可工程化、可量化、可持续优化的组织问题**，同时充分发挥 AI 在**无限并行、无疲劳、完美记忆、高速反馈**上的超人类优势。

---

## 5. 核心概念

### 5.1 用户术语 vs 技术术语

| 用户术语（对外）     | 技术术语（对内）     | 说明 |
|---------------------|---------------------|------|
| **Team**            | Team                | 团队 |
| **Team Member**     | **Role Instance**   | 虚拟团队成员（核心执行单元） |
| **Role**            | Role                | 岗位定义 |
| **Skill**           | Skill               | 能力证书 |
| **Soul**            | Soul                | 专业人格 |
| **Actor**           | Actor               | LLM 执行实例 |
| **Orchestrator**    | Orchestrator        | 智能编排器 |

### 5.2 详细概念定义

**Team（团队）**  
一组 Role 的集合，可分为静态模板和运行时实例。

**Team Member（虚拟团队成员）**  
实际执行任务的 AI 员工。其**底层实现**为 **Role Instance**，即 Role（岗位）与 Actor（具体模型）在运行时的动态绑定实例，携带上下文、记忆和实时状态。

**Role（角色）**  
静态岗位定义，相当于人类组织中的职位说明书（Job Description）。是组织的永久资产。

**Soul（灵魂）**  
独立的专业人格和工作风格，可跨 Role 复用和切换。

**Skill（技能）**  
原子化的专业能力证书，支持 N:M 绑定，是可共享、可进化、可交易的组织资产。Skill 关注“角色具备什么专业能力”，而非具体工具调用（工具和模型仅为实现介质）。

**Actor（执行者）**  
具体的 LLM 模型实例（可随时替换）。

**Orchestrator（编排器）**  
系统的智能管理层，负责任务分解、Team Member 招募与分配、调度、监控、路由和进化触发。

---

## 6. 竞品定位与分层架构

### 6.1 分层架构

| 层级 | 名称 | 定位 | 代表技术 |
|------|------|------|----------|
| **战略层** | Vision | 产品愿景 | OpenAI Workhorse |
| **组织管理层** | Framework | Role、Team Member、记忆、进化 | **RAMS**（核心） |
| **执行引擎层** | Runtime / Adapter | 具体任务执行、工具调用 | Codex CLI、Claude Code、OpenClaw 等 |
| **基础模型层** | Foundation Models | 算力提供者 | GPT-5.4/5.5、Claude 4 等 |

### 6.2 主要竞品定位

| 竞品 / 技术 | 所属层级 | 在 RAMS 中的角色 | 详细说明 |
|------------|----------|------------------|----------|
| **GPT-5.4 / GPT-5.5** | 基础模型层 | **Actor** 主力 | 顶级推理能力提供者 |
| **Codex CLI** | 执行引擎层 | **首选 Runtime Adapter** | 强大的 CLI 执行环境 |
| **Claude Code** | 执行引擎层 | **重要 Runtime Adapter** | 原生支持 Agent Teams 和 MCP |
| **OpenClaw** | 执行引擎层 | **工具集成平台** | 提供大量面向具体工具的 Skill，本质是工具调用集合 |
| **Windsurf** | 执行引擎层 | **Runtime Adapter** | Cascade 工作流补充 |
| **oh-my-openagent / oh-my-codex** | 执行引擎层 | **工程实践参考** | 成熟的多 Agent 实现 |

**RAMS 与 OpenClaw 的核心区别**：OpenClaw 的 Skill 主要是具体工具集成，而 RAMS 的 Skill 是抽象的专业能力证书。RAMS 可在其之上构建更高层次的组织管理能力。

---

## 7. 五层记忆架构

所有记忆归属于 **Role**（组织资产）：

1. **L1 Prompt Memory** —— 最稳定层（核心提示词、最佳实践）
2. **L2 Session Archive** —— 原始会话记录（提炼原料）
3. **L3 Skill Memory** —— 技能级最佳实践（支持跨 Role 知识授粉）
4. **L4 Vector Index** —— 向量检索加速层
5. **L5 User Profile** —— 用户个性化画像

**核心价值**：实现**团队越用越聪明**，知识永不随 Actor 更换而丢失。

---

## 8. 系统运行流程

1. 用户输入任务 → Orchestrator 解析并分解
2. 招募 Team Member（动态或模板化）
3. Team Member 实例化（绑定 Actor + 加载 Soul、Skills、Memory）
4. 并行执行 + Orchestrator 监控路由
5. 任务结束 → 经验提炼进入五层记忆
6. 触发双轨进化，持续优化 Role 与 Actor

---

## 9. 项目结构（.open-workhorse）

```
.open-workhorse/                  # Single Source of Truth
├── config.yaml
├── teams/                        # 团队模板
├── roles/{role-name}/
│   ├── role.yaml
│   ├── soul.md
│   └── default-skills.yaml
├── skills/                       # 独立 Skill 资产
├── memory/                       # 五层组织记忆
├── scores/                       # Team Member 评分数据
└── marketplace/                  # 已安装的市场资源
```

---

## 10. 优势与定位

- **对比基础模型**：高效使用 GPT-5.5、Claude 等顶级 Actor
- **对比执行引擎**：通过 Adapter 充分复用 Codex、Claude Code、OpenClaw 等平台
- **对比人类团队**：在速度、成本、并行能力、知识积累上具有压倒性优势
- **最佳模式**：**人类战略决策 + Workhorse 大规模执行** 的混合协同

---

**文档维护声明**：
本文件为项目 **Single Source of Truth**。所有后续设计、实现、文档必须以此总纲为基准。如有调整，需同步更新本文件并记录 Architecture Decision Record (ADR)。
