<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!--                        README.md — Vibe Coding Learner                    -->
<!--                         中文为主，English sections inline                  -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->

<h1 align="center">🧠 vibe-coding-learner</h1>
<h3 align="center">从 AI Agent 对话中提炼真正的开发能力</h3>
<h4 align="center"><em>Extract Real Engineering Skills from AI Agent Conversations</em></h4>

<p align="center">
  <img src="https://img.shields.io/badge/version-2.1.0-blue" alt="version">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="license">
  <img src="https://img.shields.io/badge/platform-Claude%20Code-purple" alt="platform">
  <img src="https://img.shields.io/badge/language-中文-brightgreen" alt="language">
</p>

---

## 📦 1. 项目简介 / Project Overview

### 一句话简介 / One-Liner

**将你与 AI Agent 的开发对话（需求→设计→编码→排错→部署）转化为可内化的面试场景题、避坑清单和结构化知识库。**
*Turn your AI-agent development conversations (requirements → design → coding → debugging → deployment) into interview scenario questions, pitfall checklists, and a structured knowledge base you actually own.*

### 问题 / The Problem

Vibe Coding 时代，开发者用 AI Agent 完成从写代码、排错到部署的全流程。生产力飙升的同时，一个副作用正在蔓延：

> **离开 Agent 之后（比如面试时），开发者自身的设计能力、排错能力、运维能力变弱了。**

单独去学这些知识，又面临三个困境：
1. **资源多而杂**——网上教程与你的真实项目脱节
2. **不知道学什么**——Agent 帮你做掉了，你甚至不知道有个坑存在
3. **没有复习机制**——看过的知识几天后就忘了，无法转化为长期记忆

### 解决方案 / The Solution

vibe-coding-learner 是一个 **Claude Code Skill**，它对你与 AI Agent 的完整开发对话进行三步处理：

| 步骤 | 做什么 | 产出 |
|------|--------|------|
| 🧲 模式一·拦截记录 | 从对话中提取有价值的决策、排错思路、架构选型 | 5 维度知识信号（架构/编码/排错/部署/方法论） |
| 🎯 模式二·面试题生成 | 将知识转化为 10 类面试场景题，含反事实推理 | 可复述、可自评的结构化题库 |
| 🗄️ 模式三·知识蒸馏 | 结构化存储 + 间隔复习调度 + 过期归档 | 持续增长的个人知识库、避坑清单、复习调度表 |

**核心理念**：不是复制 Agent 做了什么，而是理解它**为什么**这么做。

> *Don't record what the agent did — understand **why** it did it.*

---

## 🗺️ 2. 目录 / Table of Contents

| 章节 | 内容 |
|------|------|
| [1. 项目简介](#1-项目简介--project-overview) | 问题、解决方案、核心理念 |
| [2. 目录](#2-目录--table-of-contents) | 本目录 |
| [3. 快速开始](#3-快速开始--quick-start) | 5 分钟上手指南 |
| [4. 核心功能](#4-核心功能--core-features) | 三大模式 + 防御机制详解 |
| [5. 安装与配置](#5-安装与配置--installation--configuration) | 各平台安装步骤 |
| [6. 使用示例](#6-使用示例--usage-examples) | 6 个典型场景完整演示 |
| [7. 工作原理](#7-工作原理--how-it-works) | 架构设计、复习算法、渐进式提醒 |
| [8. 文件结构](#8-文件结构--project-structure) | 目录树及文件说明 |
| [9. 贡献指南](#9-贡献指南--contributing) | 如何参与贡献 |
| [10. 许可证](#10-许可证--license) | MIT License |
| [11. 致谢](#11-致谢--acknowledgments) | 灵感来源与参考 |

---

## 3. 快速开始 / Quick Start

### 3.1 前置依赖 / Prerequisites

| 依赖 | 说明 |
|------|------|
| [Claude Code](https://claude.ai/code) | CLI 或 VS Code 扩展，v1.0+ |
| 一个 AI Agent 开发对话记录 | 与 Claude、Copilot、Cursor 等 Agent 的聊天历史 |
| （可选）Git | 用于版本管理你的知识库 |

### 3.2 安装 / Installation

**方式一：VS Code 扩展（推荐）**

1. 打开 VS Code，确保已安装 Claude Code 扩展
2. 将此仓库克隆到任意位置：
   ```bash
   git clone https://github.com/bb-cccc/vibe-coding-learner.git
   ```
3. 将 `vibe-coding-learner/` 目录复制到项目的 `.claude/skills/` 下：
   ```bash
   cp -r vibe-coding-learner /path/to/your-project/.claude/skills/
   ```
4. 重启 Claude Code 或输入 `/reload-skills`

**方式二：Claude Code CLI**

```bash
# 克隆仓库
git clone https://github.com/bb-cccc/vibe-coding-learner.git

# 进入你的项目目录
cd /path/to/your-project

# 链接 skill 目录
mkdir -p .claude/skills
ln -s /path/to/vibe-coding-learner .claude/skills/vibe-coding-learner
```

**方式三：全局安装（所有项目可用）**

将 `vibe-coding-learner/` 放入用户级 skills 目录：
- **macOS / Linux**：`~/.claude/skills/vibe-coding-learner/`
- **Windows**：`%USERPROFILE%\.claude\skills\vibe-coding-learner\`

### 3.3 基本用法 / Basic Usage

在 Claude Code 对话中输入以下任一触发词即可激活：

```
/vibe-coding-learner
```

或直接说：

```
帮我把上次与 Agent 的开发对话做一次复盘
从我的项目里生成一些面试题
整理一下我最近的避坑清单
```

**首次使用**时，Skill 会引导你完成 3 项自评（经验等级 / 技术栈 / 学习目标），之后生成的题目难度将自动适配。

---

## 4. 核心功能 / Core Features

### 4.1 模式一：拦截记录 / Signal Extraction

从冗长的 Agent 对话中提取 **5 个维度** 的知识信号：

| 维度 | 提取什么 | 示例信号 |
|------|----------|----------|
| 🏗️ 架构决策 | 技术选型、设计模式、权衡取舍 | "选择 X 因为..."、"对比了 A 和 B" |
| 💻 代码实现 | 关键模式、API 设计、状态管理 | 核心代码片段、重构过程 |
| 🐛 排错过程 | 错误类型、诊断路径、修复策略 | 错误信息、排查步骤、"原来是..." |
| 🚀 部署运维 | 环境配置、CI/CD、容器化 | Docker 命令、部署脚本 |
| 🧠 方法论 | 问题拆解、方案调研、迭代优化 | 任务分解、搜索策略、方案对比 |

每条知识记录 6 个要素：`上下文 → 问题/决策 → Agent 做法 → 底层原理 → 替代方案 → 可迁移教训`

### 4.2 模式二：面试题生成 / Interview Question Generation

生成 **10 类** 面试场景题：

| # | 类型 | 考察能力 |
|---|------|----------|
| 1 | 场景设计题 | 给定业务场景，设计技术方案 |
| 2 | Bug 排查题 | 给定错误现象，分析根因 |
| 3 | 深挖原理题 | 追问技术选型的底层原因 |
| 4 | 代码审查题 | 发现代码中的问题并优化 |
| 5 | 项目表达题 | 清晰表达项目背景、难点、成果 |
| 6 | 系统设计题 | 规模扩展设计 |
| 7 | 运维排障题 | 模拟线上故障排查 |
| 8 | 方案对比题 | 对比两种方案的优劣和适用场景 |
| 9 | 复盘反思题 | 回顾项目，提炼改进方向 |
| 10 | 测试质量题 | 设计测试用例 |

每道题包含：场景描述 → 问题 → 参考思路 → 答案要点 → **反事实推理** → 深挖追问

### 4.3 模式三：知识蒸馏 / Knowledge Distillation

生成 **6 个持久化文件**，形成个人知识资产：

```
knowledge/
├── interview-qa.md          # 面试题库
├── pitfall-checklist.md     # 避坑清单
├── architecture-notes.md    # 架构决策笔记
├── debugging-playbook.md    # 排错手册
├── review-schedule.md       # 复习调度表（间隔复习引擎）
├── knowledge-index.md       # 知识库索引
└── archive/                 # 已归档的过时条目
```

### 4.4 间隔复习引擎 / Spaced Repetition Engine

内置简化 [SM-2 算法](https://en.wikipedia.org/wiki/SuperMemo)，每次复述后根据掌握度（0/1/2）自动计算下次复习日期：

```
复述评分为 0（完全卡住）→ 重置为 1 天
复述评分为 1（部分回忆）→ 间隔 × 0.5（不低于 1 天）
复述评分为 2（流畅复述）→ 间隔 × 2（上限 120 天）
```

间隔序列：**1天 → 3天 → 7天 → 14天 → 30天 → 60天 → 120天**

启动 Skill 时自动检查到期复习任务，今日到期 ≤ 3 道则逐道复习，超过则优先复习评分最低的 3 道。

### 4.5 防御机制 / Defense Mechanisms

9 道防御机制确保输出质量，避免"学了个寂寞"：

| 机制 | 触发条件 | 行为 |
|------|----------|------|
| 🔍 用户确认 | AI 推断的决策理由 | 标注 `[待确认]`，反问用户 |
| ✂️ 范围限制 | 对话超过 50 轮 | 建议分段复盘 |
| 🗣️ 复述强制 | 每道题生成后 | 要求口述，自评 0/1/2 |
| 📢 渐进式提醒 | 连续跳过 ≥3 道题 | 逐级加强提醒，10 道硬暂停 |
| 🧹 信号过滤 | 提取知识点时 | 丢弃重复操作、无意义对话 |
| 🏷️ 深度标注 | 知识点深度不足 | 标注 `[待深挖]` |
| 🔗 去重合并 | 增量更新知识库 | 检测相似条目，合并而非重复 |
| ⏳ 过期审查 | 条目超过 90 天 | 提醒审查，过时条目归档 |
| 🧭 冷启动引导 | 首次使用无对话记录 | 提供启动路径，不硬凑 |

---

## 5. 安装与配置 / Installation & Configuration

### 5.1 详细安装步骤

#### macOS / Linux

```bash
# 1. 克隆仓库
git clone https://github.com/bb-cccc/vibe-coding-learner.git

# 2. 全局安装（推荐）
mkdir -p ~/.claude/skills
cp -r vibe-coding-learner ~/.claude/skills/

# 3. 或者项目级安装
cd /path/to/your-project
mkdir -p .claude/skills
ln -s /path/to/vibe-coding-learner .claude/skills/vibe-coding-learner

# 4. 验证安装
ls ~/.claude/skills/vibe-coding-learner/SKILL.md  # 应输出文件路径
```

#### Windows (PowerShell)

```powershell
# 1. 克隆仓库
git clone https://github.com/bb-cccc/vibe-coding-learner.git

# 2. 全局安装
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills"
Copy-Item -Recurse vibe-coding-learner "$env:USERPROFILE\.claude\skills\"

# 3. 验证安装
Test-Path "$env:USERPROFILE\.claude\skills\vibe-coding-learner\SKILL.md"
# 应输出 True
```

### 5.2 配置说明

Skill 的核心配置在 `SKILL.md` 的 frontmatter 中：

```yaml
---
name: vibe-coding-learner
description: >-     # 描述与触发条件（可自定义触发词）
  ...
metadata:
  version: "2.1.0"  # Skill 版本
  tags:              # 可自定义标签
    - interview-prep
    - knowledge-extraction
    - vibe-coding
---
```

可自定义项：
- **触发词**：在 `description` 字段的 `Triggers:` 后追加你的自定义触发词
- **每日复习上限**：默认 5 道，可在 `复习提醒机制` 段落中修改
- **知识库输出路径**：默认为 `knowledge/`，可在 `模式三` 段落中修改

### 5.3 跨平台兼容性

| 平台 | Claude Code 版本 | 支持状态 |
|------|-----------------|----------|
| VS Code (Windows/macOS/Linux) | Claude Code 扩展 v1.0+ | ✅ 完全支持 |
| CLI (macOS/Linux) | claude CLI v1.0+ | ✅ 完全支持 |
| Web (claude.ai/code) | Web 版 | ✅ 支持（手动粘贴 SKILL.md 内容） |
| JetBrains IDEs | Claude Code 插件 | ✅ 完全支持 |
| 其他 Agent 平台 | N/A | ⚠️ 通用格式，需手动适配（见 [示例四](references/examples.md#示例四在-claude-code--codex-中使用)） |

---

## 6. 使用示例 / Usage Examples

### 示例一：复盘一次 Docker 排错对话 → 生成面试题

**输入**：粘贴一段 Agent 帮你排查 Docker 容器启动失败的对话。

**Skill 处理流程**：

1. **模式一**：提取 5 个知识点（Alpine 缺少运行时、Docker 镜像分层、多阶段构建等）
2. **模式二**：生成面试题——

> ### [Bug 排查题] Docker 容器启动后立即退出
> **难度**：基础
>
> 你刚把一个 Python Web 应用容器化，执行 `docker run` 后容器立刻退出。
> `docker logs` 显示 `"executable file not found in $PATH"`。
>
> **问题**：你的排查思路是什么？
>
> **反事实推理**：
> - 如果这是 Node.js 应用，排查思路有什么不同？
> - 如果公司安全策略要求必须用 Alpine，你怎么处理？

3. **模式三**：知识库追加 1 道面试题 + 1 条避坑条目

完整演示见 [示例一](references/examples.md#示例一从排错对话中提炼知识)

---

### 示例二：从架构对话提炼方案对比题

**输入**：你描述了一个"Agent 建议用 PostgreSQL + Neo4j 双数据库"的架构决策。

**Skill 生成**：

> ### [方案对比题] 为什么用 PostgreSQL + Neo4j 而不是全部 Neo4j？
> **难度**：进阶
>
> **反事实推理**：
> - 如果团队所有人熟悉 Neo4j，还会选双库吗？
> - 如果图查询只占 5% 请求，双库运维成本还值得吗？
> - PostgreSQL 的 Apache AGE 扩展能否替代 Neo4j？

完整演示见 [示例二](references/examples.md#示例二从架构设计对话中提炼知识)

---

### 示例三：间隔复习流程

三天前完成的复盘，今天启动 Skill 时：

```
AI：欢迎回来！

📋 复习检查中... review-schedule.md 已加载

今日到期复习：3 道题
🟡 Q-001 Redis 缓存策略 — 上次评分 1 — 间隔 3 天
🟡 Q-003 Docker 容器排查 — 上次评分 1 — 间隔 1 天
🟡 Q-007 PostgreSQL vs MongoDB — 上次评分 0 — 间隔 1 天

今天先处理到期复习，还是开始一次新的复盘？
```

完整演示见 [示例五](references/examples.md#示例五间隔复习流程)

---

### 示例四：冷启动（首次使用）

无历史对话记录时，Skill 不会硬凑，而是提供具体的启动路径：

```
AI：因为没有现成的对话记录，给你一个最小启动路径：

1. 下次用 Agent 开发时，在对话开头说"请在做关键决策时解释你的理由"
2. 关注 Agent 的"选择 X 而不是 Y"、"排查步骤"等信号
3. 建议 3-5 天内完成一次有意义的开发后回来复盘
```

完整演示见 [示例零](references/examples.md#示例零冷启动流程)

---

### 示例五：季度归档审查

使用超过 90 天后，自动触发审查：

```
AI：📦 季度知识库审查

超过 180 天（3 条）——建议优先处理：
  - Q-002 Angular 组件通信 — 2026-01-10 — Angular 15
  - 坑-003 Webpack 配置优化 — 2025-12-20 — Webpack 4
  - KB-005 jQuery AJAX 全局配置 — 2025-11-15 — jQuery 3.6

每条回复：[仍有效] / [已过时] / [已替代] / [稍后审查]
```

完整演示见 [示例六](references/examples.md#示例六季度归档审查)

---

## 7. 工作原理 / How It Works

### 7.1 整体架构

```
┌─────────────────────────────────────────────────────────┐
│                    用户输入 / User Input                  │
│        （Agent 对话记录 / 项目描述 / 手动构造）             │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│              第零步：画像 & 范围确认                       │
│     · 经验等级（初级/中级/高级） → 难度自适应              │
│     · 复盘范围（需求/架构/编码/排错/部署）                 │
│     · 输入源选择（对话/项目/组合/热复盘）                   │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│              模式一：拦截记录 / Signal Extraction          │
│     · 5 维度扫描（架构/编码/排错/部署/方法论）             │
│     · 6 要素记录（上下文→问题→做法→原理→替代→迁移）         │
│     · 信号过滤 + [待确认] 标注                            │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│           模式二：面试题生成 / Question Generation         │
│     · 10 类面试题（难度按画像自适应）                      │
│     · 反事实推理（强制） + 深挖追问                        │
│     · 口述复述 → 自评 0/1/2 → 卡住诊断                    │
│     · 渐进式提醒（跳过 3/6/10 道递增强度）                 │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│          模式三：知识蒸馏 / Knowledge Distillation         │
│     · 生成 6 个持久化文件（题库/避坑/复习调度表等）        │
│     · SM-2 间隔复习引擎 → 自动计算下次复习日期              │
│     · 知识衰减检测（90/180/365 天） → 季度归档审查         │
│     · 增量去重合并                                        │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│           持续复习循环 / Continuous Review Loop           │
│     启动 Skill → 检查到期任务 → 复习+评分 → 更新间隔       │
└─────────────────────────────────────────────────────────┘
```

### 7.2 SM-2 间隔复习算法

```
评分 0（完全卡住）──────► 间隔 = 1 天（重新记忆）
评分 1（部分回忆）──────► 间隔 = 当前间隔 × 0.5（不低于 1 天）
评分 2（流畅复述）──────► 间隔 = 当前间隔 × 2（上限 120 天）

初始间隔：1 天
间隔序列：1 → 3 → 7 → 14 → 30 → 60 → 120 天
```

### 7.3 难度自适应

根据用户经验等级调整题目难度分布：

| 经验等级 | 基础题 | 进阶题 | 高级题 |
|----------|:------:|:------:|:------:|
| 初级 (<2年) | 50% | 35% | 15% |
| 中级 (2-5年) | 20% | 50% | 30% |
| 高级 (5年+) | 10% | 30% | 60% |

---

## 8. 文件结构 / Project Structure

```
vibe-coding-learner/
│
├── SKILL.md                          # ★ Skill 主文件（核心指令与工作流定义）
│   ├── 目标与触发条件                  #    Skill 定位与激活条件
│   ├── 用户画像与冷启动                #    自评画像、难度自适应、无对话时的引导
│   ├── 核心原则                        #    "追问为什么"的指导思想
│   ├── 完整工作流                      #
│   │   ├── 第零步：输入源与复盘范围     #    四种输入模式 + 分段策略
│   │   ├── 模式一：拦截记录             #    5维度 × 6要素提取 + 过滤规则
│   │   ├── 模式二：面试题生成           #    10类题 × 复述机制 × 渐进式提醒
│   │   └── 模式三：知识蒸馏             #    知识库生成 + SM-2复习引擎 + 归档机制
│   ├── 防御机制汇总（9道）              #    质量保障体系
│   ├── 输出指令                        #    中文输出强制规则
│   ├── 边界情况处理                    #    输入过短/过长/无学习点等处理策略
│   └── 附加资源引用                    #    指向 templates.md / examples.md
│
├── assets/
│   └── templates.md                   # 输出格式模板（7 套）
│       ├── 模板一：面试题卡片           #    含掌握度自评、下次复习日期、归档状态
│       ├── 模板二：避坑条目             #    现象→原因→解决→预防 完整链路
│       ├── 模板三：知识库条目           #    含技术栈版本、归档状态、审查日期
│       ├── 模板四：知识库索引           #    全量题库/避坑/知识条目的索引格式
│       ├── 模板四附加：复习调度卡片     #    含复习历史表、间隔变化、掌握状态
│       ├── 模板五：归档记录             #    归档日志 + 按原因分类汇总
│       ├── 模板六：归档条目头           #    已归档条目的警示标记
│       └── 模板七：单次复盘报告         #    完整复盘报告输出格式
│
├── references/
│   └── examples.md                    # 完整使用示例（6 个场景）
│       ├── 示例零：冷启动流程           #    首次使用、无对话记录的交互演示
│       ├── 示例一：排错对话 → 知识提炼   #    Docker 排错完整三模式处理示例
│       ├── 示例二：架构对话 → 方案对比题 #    PostgreSQL+Neo4j 双库选型示例
│       ├── 示例三：完整复盘对话流程      #    含难度自适应、掌握度自评、渐进提醒
│       ├── 示例四：Claude Code 安装使用  #    跨平台安装说明
│       ├── 示例五：间隔复习流程          #    SM-2 复习交互完整演示
│       └── 示例六：季度归档审查         #    90/180天审查交互演示
│
├── README.md                          # ★ 本文件（项目说明文档）
└── LICENSE                            # MIT License
```

### 运行时生成的知识库目录（由模式三创建）

```
your-project/knowledge/                # ← 在你的项目目录下生成
├── interview-qa.md                    # 面试题库（按 10 类题型组织）
├── pitfall-checklist.md               # 避坑清单（按编码/部署/架构阶段分类）
├── architecture-notes.md              # 架构决策笔记
├── debugging-playbook.md              # 排错手册
├── review-schedule.md                 # 复习调度表（间隔复习引擎）
├── knowledge-index.md                 # 知识库索引（自动维护统计数字）
└── archive/                           # 已归档的过时条目
    ├── archived-qa.md
    ├── archived-pitfalls.md
    └── archive-log.md
```

---

## 9. 贡献指南 / Contributing

欢迎贡献！无论是 Bug 报告、功能建议还是 Pull Request。

### 如何报告 Bug

1. 在 [Issues](https://github.com/bb-cccc/vibe-coding-learner/issues) 中创建新 Issue
2. 描述你使用的 Claude Code 版本、操作系统、触发场景
3. 附上相关的错误输出或异常行为描述

### 如何提交功能建议

1. 在 Issues 中创建新 Issue，选择 "Feature Request" 标签
2. 描述：这个功能解决什么问题？期望的使用流程是怎样的？
3. 如果可能，附上参考或草图

### Pull Request 流程

```bash
# 1. Fork 仓库
# 2. 创建特性分支
git checkout -b feature/my-new-feature

# 3. 提交更改（遵循 Conventional Commits）
git commit -m "feat: add xxx feature"
# 或者
git commit -m "fix: correct xxx behavior"

# 4. 推送到你的 Fork
git push origin feature/my-new-feature

# 5. 创建 Pull Request
```

### 提交规范

- 使用 [Conventional Commits](https://www.conventionalcommits.org/) 格式
- PR 标题简洁（< 70 字符），描述详细
- 如果修改 SKILL.md 核心逻辑，请同步更新 `templates.md` 和 `examples.md`

---

## 10. 许可证 / License

本项目采用 [MIT License](https://opensource.org/licenses/MIT)。

```
MIT License

Copyright (c) 2026 vibe-coding-learner contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
...
```

简言之：你可以自由使用、修改、分发本项目，但需保留原始版权声明。

---

## 11. 致谢 / Acknowledgments

本项目受益于以下工作与思想：

| 项目/思想 | 关联 |
|-----------|------|
| [SuperMemo SM-2 Algorithm](https://en.wikipedia.org/wiki/SuperMemo) | 间隔复习算法原型 |
| [Anki](https://apps.ankiweb.net/) | 间隔复习系统的现代实践 |
| [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) | Skill 系统架构参考 |
| [Conventional Commits](https://www.conventionalcommits.org/) | 提交规范 |
| [反事实推理 (Counterfactual Reasoning)](https://plato.stanford.edu/entries/causation-counterfactual/) | 面试题设计核心方法论 |

特别感谢所有在 Vibe Coding 领域探索的开发者——这个问题值得被认真对待。

---

<p align="center">
  <sub>Made with ❤️ for developers who refuse to let AI think for them.</sub>
  <br>
  <sub>为那些拒绝让 AI 替自己思考的开发者而建。</sub>
</p>
