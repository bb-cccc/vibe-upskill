<h1 align="center">🧠 vibe-upskill</h1>
<h3 align="center">Extract Real Engineering Skills from AI Agent Conversations</h3>
<h3 align="center">Review Your Vibe Coding Sessions — Auto-Generate Interview Questions & Knowledge Base</h3>

<p align="center">
  <img src="https://img.shields.io/badge/version-2.2.0-blue" alt="version">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="license">
  <img src="https://img.shields.io/badge/platform-Universal_AI_Agent-orange" alt="platform">
  <img src="https://img.shields.io/badge/language-English-brightgreen" alt="language">
</p>

<p align="center">
  <a href="README_CN.md">中文版</a>
</p>

---

## 📦 1. Project Overview

### One-Liner

**Turn your AI-agent development conversations (requirements → design → coding → debugging → deployment) into interview scenario questions, pitfall checklists, and a structured knowledge base you actually own.**

### The Problem

In the era of Vibe Coding, developers use AI Agents for everything from writing code to debugging and deployment. Productivity is soaring, but a side effect is spreading:

> **When you step away from the Agent (e.g., during an interview), your own design, debugging, and ops skills have atrophied.**

Trying to learn these skills on your own faces three obstacles:
1. **Information overload** — online tutorials are disconnected from your real projects
2. **Unknown unknowns** — the Agent handled it for you, so you don't even know the pitfall exists
3. **No review mechanism** — knowledge fades after days without a system to convert it into long-term memory

### The Solution

vibe-upskill is a **universal AI Agent Skill** — essentially a carefully designed system prompt that works with Claude Code, Cursor, ChatGPT, Copilot Chat, and any other AI Agent. It processes your full development conversations with AI Agents in three steps:

| Step | What It Does | Output |
|------|-------------|--------|
| 🧲 Mode 1 · Signal Extraction | Extract valuable decisions, debugging insights, and architecture choices from conversations | 5-dimension knowledge signals (Architecture / Coding / Debugging / Deployment / Methodology) |
| 🎯 Mode 2 · Question Generation | Transform knowledge into 10 types of interview scenario questions with counterfactual reasoning | Structured, self-assessable question bank |
| 🗄️ Mode 3 · Knowledge Distillation | Structured storage + spaced repetition scheduling + expiry archiving | Growing personal knowledge base, pitfall checklist, review schedule |

**Core philosophy**: Don't record what the agent did — understand **why** it did it.

---

## 🗺️ 2. Table of Contents

| Section | Content |
|---------|---------|
| [1. Project Overview](#1-project-overview) | Problem, solution, core philosophy |
| [2. Table of Contents](#2-table-of-contents) | This section |
| [3. Quick Start](#3-quick-start) | 5-minute guide |
| [4. Core Features](#4-core-features) | Three modes + defense mechanisms |
| [5. Configuration](#5-configuration) | Customizable options |
| [6. Usage Examples](#6-usage-examples) | 6 complete scenario demos |
| [7. How It Works](#7-how-it-works) | Architecture, review algorithm, progressive reminders |
| [8. Project Structure](#8-project-structure) | Directory tree and file descriptions |
| [9. Contributing](#9-contributing) | How to contribute |
| [10. License](#10-license) | MIT License |
| [11. Acknowledgments](#11-acknowledgments) | Inspirations and references |

---

## 3. Quick Start

### 3.1 Prerequisites

| Requirement | Details |
|-------------|---------|
| Any AI Agent | Claude Code, Cursor, ChatGPT, Copilot Chat, etc. |
| An AI Agent development conversation | Chat history from Claude, Copilot, Cursor, etc. |
| (Optional) Git | For versioning your knowledge base |

### 3.2 Installation

Send the following to any AI Agent (Claude Code, Cursor, Copilot, ChatGPT, etc.):

```
Help me install this Skill: https://github.com/bb-cccc/vibe-upskill
```

The Agent will clone, install to the correct directory, and verify the installation automatically. No manual commands needed.

### 3.3 Basic Usage

After installation, describe your review needs in conversation to activate:

```
Example 1: Help me review [conversation name], e.g. "yesterday's Docker debugging session"
Example 2: Generate interview questions based on [conversation name]
Example 3: Organize my recent pitfall checklist
```

**On first use**, the Skill will guide you through a 3-item self-assessment (preparation stage / tech stack / learning goals). Generated questions will then auto-adapt to your difficulty level.

---

## 4. Core Features

### 4.1 Mode 1: Signal Extraction

Extract knowledge signals across **5 dimensions** from lengthy Agent conversations:

| Dimension | What It Extracts | Example Signals |
|-----------|-----------------|-----------------|
| 🏗️ Architecture Decisions | Tech choices, design patterns, trade-offs | "Chose X because...", "Compared A vs. B" |
| 💻 Code Implementation | Key patterns, API design, state management | Core code snippets, refactoring process |
| 🐛 Debugging Process | Error types, diagnostic paths, fix strategies | Error messages, troubleshooting steps, "Turns out..." |
| 🚀 Deployment & Ops | Environment config, CI/CD, containerization | Docker commands, deployment scripts |
| 🧠 Methodology | Problem decomposition, research, iteration | Task breakdown, search strategies, solution comparison |

Each knowledge entry records 6 elements: `Context → Problem/Decision → Agent's Approach → Underlying Principles → Alternatives → Transferable Lessons`

### 4.2 Mode 2: Interview Question Generation

Generates **10 types** of interview scenario questions:

| # | Type | What It Tests |
|---|------|---------------|
| 1 | Scenario Design | Design a technical solution for a given business scenario |
| 2 | Bug Investigation | Analyze root cause from error symptoms |
| 3 | Deep-Dive Principles | Probe the underlying reasons behind tech choices |
| 4 | Code Review | Identify issues in code and optimize |
| 5 | Project Communication | Clearly articulate project background, challenges, and outcomes |
| 6 | System Design | Scale-oriented architecture design |
| 7 | Ops Troubleshooting | Simulated production incident investigation |
| 8 | Solution Comparison | Compare pros/cons and applicable contexts of two approaches |
| 9 | Retrospective | Review a project and identify improvement directions |
| 10 | Test Quality | Design test cases |

Each question includes: Scenario → Problem → Reference Approach → Key Points → **Counterfactual Reasoning** → Follow-up Probes

### 4.3 Mode 3: Knowledge Distillation

Generates **6 persistent files**, forming a personal knowledge asset:

```
knowledge/
├── interview-qa.md          # Interview question bank
├── pitfall-checklist.md     # Pitfall checklist
├── architecture-notes.md    # Architecture decision notes
├── debugging-playbook.md    # Debugging playbook
├── review-schedule.md       # Review schedule (spaced repetition engine)
├── knowledge-index.md       # Knowledge base index
└── archive/                 # Archived outdated entries
```

### 4.4 Spaced Repetition Engine

Built-in simplified [SM-2 algorithm](https://en.wikipedia.org/wiki/SuperMemo). After each recall attempt, the next review date is auto-calculated based on mastery level (0/1/2):

```
Score 0 (completely stuck) → Reset to 1 day
Score 1 (partial recall)   → Interval × 0.5 (min 1 day)
Score 2 (fluent recall)    → Interval × 2 (max 120 days)
```

Interval sequence: **1d → 3d → 7d → 14d → 30d → 60d → 120d**

On Skill launch, review tasks due today are checked automatically. If ≤ 3 items are due, review them one by one. If more, prioritize the 3 with the lowest scores.

### 4.5 Defense Mechanisms

9 defense mechanisms ensure output quality:

| Mechanism | Trigger Condition | Behavior |
|-----------|-------------------|----------|
| 🔍 User Confirmation | AI-inferred decision rationale | Mark `[To Confirm]`, ask user |
| ✂️ Scope Limiting | Conversation exceeds 50 turns | Suggest segmenting the review |
| 🗣️ Recall Enforcement | After each question is generated | Require verbal recall, self-score 0/1/2 |
| 📢 Progressive Reminders | ≥ 3 questions skipped consecutively | Escalating reminders; hard pause at 10 |
| 🧹 Signal Filtering | When extracting knowledge | Discard repetitive ops and low-signal dialogue |
| 🏷️ Depth Tagging | Superficial knowledge points | Mark `[Needs Deep Dive]` |
| 🔗 Dedup & Merge | Incremental knowledge base updates | Detect similar entries, merge instead of duplicate |
| ⏳ Expiry Review | Entry exceeds 90 days | Remind for review; archive outdated entries |
| 🧭 Cold Start Guidance | First use with no conversation history | Provide a startup path; don't fabricate |

---

## 5. Configuration

vibe-upskill's core instructions reside in `SKILL.md`. The following can be customized:

- **Trigger words**: Append your custom triggers after `Triggers:` in the `description` field
- **Daily review cap**: Default 5 questions; modify in the "Review Reminder" section
- **Knowledge base output path**: Default `knowledge/`; modify in the "Mode 3" section
- **Preparation stage**: The Skill guides you through a self-assessment on first use; difficulty distribution can be manually adjusted later

For further customization, edit the relevant paragraph in [SKILL.md](SKILL.md) directly — the entire Skill is a readable prompt with no hidden black-box logic.

---

## 6. Usage Examples

### Example 1: Review a Docker Debugging Session → Generate Interview Questions

**Input 1**: Paste a conversation where the Agent helped troubleshoot a Docker container startup failure.
**Input 2**: Tell the Agent the session name directly.

**Skill processing flow**:

1. **Mode 1**: Extract 5 knowledge points (Alpine missing runtime, Docker image layering, multi-stage builds, etc.)
2. **Mode 2**: Generate interview questions —

> ### [Bug Investigation] Docker Container Exits Immediately After Startup
> **Difficulty**: Basic
>
> You just containerized a Python web app. Running `docker run` causes the container to exit immediately.
> `docker logs` shows `"executable file not found in $PATH"`.
>
> **Question**: What's your troubleshooting approach?
>
> **Counterfactual Reasoning**:
> - How would your approach differ for a Node.js application?
> - If your company's security policy requires Alpine, how would you handle this?

3. **Mode 3**: Append 1 interview question + 1 pitfall entry to the knowledge base

Full demo: [Example 1](references/examples.md#example-1-extracting-knowledge-from-debugging-sessions)

---

### Example 2: Extract Solution Comparison Questions from Architecture Discussions

**Input**: You describe an architecture decision where "the Agent recommended PostgreSQL + Neo4j dual-database."

**Skill generates**:

> ### [Solution Comparison] Why PostgreSQL + Neo4j Instead of All Neo4j?
> **Difficulty**: Intermediate
>
> **Counterfactual Reasoning**:
> - If everyone on the team was proficient with Neo4j, would you still choose dual-database?
> - If graph queries account for only 5% of requests, is the dual-database ops overhead worth it?
> - Could PostgreSQL's Apache AGE extension replace Neo4j?

Full demo: [Example 2](references/examples.md#example-2-extracting-knowledge-from-architecture-design-discussions)

---

### Example 3: Spaced Repetition Review Flow

Three days after a review session, when launching the Skill:

```
AI: Welcome back!

📋 Checking reviews... review-schedule.md loaded

Due today: 3 questions
🟡 Q-001 Redis Caching Strategy — Last score 1 — Interval 3 days
🟡 Q-003 Docker Container Troubleshooting — Last score 1 — Interval 1 day
🟡 Q-007 PostgreSQL vs MongoDB — Last score 0 — Interval 1 day

Start with due reviews or begin a new review session?
```

Full demo: [Example 5](references/examples.md#example-5-spaced-repetition-flow)

---

### Example 4: Cold Start (First Use)

When there is no conversation history, the Skill provides a concrete startup path instead of fabricating content:

```
AI: Since there are no existing conversation records, here's a minimal startup path:

1. Next time you develop with an Agent, say "please explain your reasoning for key decisions" at the start
2. Watch for signals like "chose X over Y", troubleshooting steps, etc.
3. Come back to review after a meaningful development session within 3-5 days
```

Full demo: [Example 0](references/examples.md#example-0-cold-start-flow)

---

### Example 5: Quarterly Archival Review

After 90+ days of use, an automatic review triggers:

```
AI: 📦 Quarterly Knowledge Base Review

Over 180 days (3 entries) — Suggest handling first:
  - Q-002 Angular Component Communication — 2026-01-10 — Angular 15
  - Pitfall-003 Webpack Config Optimization — 2025-12-20 — Webpack 4
  - KB-005 jQuery AJAX Global Config — 2025-11-15 — jQuery 3.6

Respond per entry: [Still Valid] / [Outdated] / [Superseded] / [Review Later]
```

Full demo: [Example 6](references/examples.md#example-6-quarterly-archival-review)

---

## 7. How It Works

### 7.1 Overall Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     User Input                           │
│      (Agent conversation logs / project descriptions)    │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│           Step Zero: Profile & Scope Confirmation        │
│     · Preparation stage → Difficulty auto-adaptation     │
│     · Review scope (requirements/architecture/coding/    │
│       debugging/deployment)                              │
│     · Input source selection (conversation / live capture)│
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│           Mode 1: Signal Extraction                      │
│     · 5-dimension scanning                               │
│     · 6-element recording (Context→Problem→Approach→     │
│       Principles→Alternatives→Transfer)                   │
│     · Signal filtering + [To Confirm] tagging            │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│           Mode 2: Question Generation                    │
│     · 10 question types (difficulty auto-adapted)        │
│     · Counterfactual reasoning (mandatory) + deep probes │
│     · Verbal recall → Self-score 0/1/2 → Stuck diagnosis│
│     · Progressive reminders (escalating at 3/6/10)       │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│           Mode 3: Knowledge Distillation                 │
│     · Generate 6 persistent files                        │
│     · SM-2 spaced repetition engine → Auto-calculate     │
│       next review dates                                  │
│     · Knowledge decay detection (90/180/365 days)        │
│     · Incremental dedup & merge                          │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────┐
│        Continuous Review Loop                            │
│     Launch Skill → Check due tasks → Review + Score →    │
│     Update intervals                                     │
└─────────────────────────────────────────────────────────┘
```

### 7.2 SM-2 Spaced Repetition Algorithm

```
Score 0 (completely stuck) ──► Interval = 1 day (re-memorize)
Score 1 (partial recall)   ──► Interval = current × 0.5 (min 1 day)
Score 2 (fluent recall)    ──► Interval = current × 2 (max 120 days)

Initial interval: 1 day
Interval sequence: 1 → 3 → 7 → 14 → 30 → 60 → 120 days
```

### 7.3 Difficulty Auto-Adaptation

Question difficulty distribution adjusts based on the user's preparation stage:

| Stage | Basic | Intermediate | Advanced |
|-------|:-----:|:------------:|:--------:|
| Foundation | 35% | 50% | 15% |
| Skill Building | 15% | 55% | 30% |
| Gap Filling | 10% | 45% | 45% |

---

## 8. Project Structure

```
vibe-upskill/
│
├── SKILL.md                          # ★ Main Skill file (core instructions & workflow)
│   ├── Goals & Triggers              #    Skill positioning and activation conditions
│   ├── User Profile & Cold Start     #    Self-assessment, difficulty adaptation, no-data guidance
│   ├── Core Principles               #    "Ask why" guiding philosophy
│   ├── Full Workflow                 #
│   │   ├── Step Zero: Input & Scope  #    Two input modes + segmentation strategy
│   │   ├── Mode 1: Signal Extraction #    5 dimensions × 6 elements + filtering rules
│   │   ├── Mode 2: Question Gen      #    10 question types × recall × progressive reminders
│   │   └── Mode 3: Knowledge Distill #    KB generation + SM-2 engine + archival mechanism
│   ├── Defense Mechanisms (9 total)  #    Quality assurance system
│   ├── Output Instructions           #    Output formatting rules
│   ├── Edge Case Handling            #    Too short / too long / no learning points
│   └── Resource References           #    Pointers to templates.md / examples.md
│
├── assets/
│   └── templates.md                   # Output format templates (7 sets)
│       ├── Template 1: Interview Card #    Mastery self-score, next review date, archive status
│       ├── Template 2: Pitfall Entry  #    Symptom → Cause → Fix → Prevention chain
│       ├── Template 3: KB Entry       #    Tech stack version, archive status, review date
│       ├── Template 4: KB Index       #    Full index format for Q&A / pitfalls / KB entries
│       ├── Template 4a: Review Card   #    Review history, interval changes, mastery status
│       ├── Template 5: Archive Record #    Archive log + summaries by cause
│       ├── Template 6: Archived Header#    Warning markers for archived entries
│       └── Template 7: Review Report  #    Complete review session output format
│
├── references/
│   └── examples.md                    # Full usage examples (6 scenarios)
│       ├── Example 0: Cold Start      #    First use, no conversation records
│       ├── Example 1: Debugging → KB  #    Docker debugging full three-mode processing
│       ├── Example 2: Architecture    #    PostgreSQL+Neo4j dual-database selection
│       ├── Example 3: Full Flow       #    Difficulty adaptation, self-assessment, reminders
│       ├── Example 4: Installation    #    Cross-platform Claude Code setup
│       ├── Example 5: Spaced Review   #    SM-2 review interaction complete demo
│       └── Example 6: Archival Review #    90/180-day review interaction demo
│
├── README.md                          # ★ This file (English)
├── README_CN.md                       # Chinese README
├── CHANGELOG.md                       # Version changelog
└── LICENSE                            # MIT License
```

### Runtime-generated Knowledge Base Directory (created by Mode 3)

```
your-project/knowledge/                # ← Generated in your project directory
├── interview-qa.md                    # Interview question bank (organized by 10 types)
├── pitfall-checklist.md               # Pitfall checklist (by coding/deployment/architecture phase)
├── architecture-notes.md              # Architecture decision notes
├── debugging-playbook.md              # Debugging playbook
├── review-schedule.md                 # Review schedule (spaced repetition engine)
├── knowledge-index.md                 # Knowledge base index (auto-maintained stats)
└── archive/                           # Archived outdated entries
    ├── archived-qa.md
    ├── archived-pitfalls.md
    └── archive-log.md
```

---

## 9. Contributing

Contributions are welcome! Bug reports, feature suggestions, and Pull Requests are appreciated.

### How to Report a Bug

1. Create a new issue in [Issues](https://github.com/bb-cccc/vibe-upskill/issues)
2. Describe your Claude Code version, operating system, and trigger scenario
3. Attach relevant error output or unexpected behavior description

### How to Submit a Feature Request

1. Create a new issue with the "Feature Request" label
2. Describe: What problem does this feature solve? What's the expected usage flow?
3. Attach references or sketches if available

### Pull Request Process

```bash
# 1. Fork the repository
# 2. Create a feature branch
git checkout -b feature/my-new-feature

# 3. Commit changes (follow Conventional Commits)
git commit -m "feat: add xxx feature"
# or
git commit -m "fix: correct xxx behavior"

# 4. Push to your fork
git push origin feature/my-new-feature

# 5. Create a Pull Request
```

### Commit Conventions

- Use [Conventional Commits](https://www.conventionalcommits.org/) format
- Keep PR titles concise (< 70 characters), descriptions detailed
- If modifying SKILL.md core logic, sync updates to `templates.md` and `examples.md`

---

## 10. License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

```
MIT License

Copyright (c) 2026 vibe-upskill contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
...
```

In short: you are free to use, modify, and distribute this project, provided you retain the original copyright notice.

---

## 11. Acknowledgments

This project benefits from the following work and ideas:

| Project / Idea | Relevance |
|----------------|-----------|
| [SuperMemo SM-2 Algorithm](https://en.wikipedia.org/wiki/SuperMemo) | Spaced repetition algorithm prototype |
| [Anki](https://apps.ankiweb.net/) | Modern practice of spaced repetition systems |
| [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) | Skill system architecture reference |
| [Conventional Commits](https://www.conventionalcommits.org/) | Commit convention |
| [Counterfactual Reasoning](https://plato.stanford.edu/entries/causation-counterfactual/) | Core methodology for interview question design |

Special thanks to all developers exploring the Vibe Coding frontier — this problem deserves to be taken seriously.

---

<p align="center">
  <sub>Made with ❤️ for developers who refuse to let AI think for them.</sub>
</p>
