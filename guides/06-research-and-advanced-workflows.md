# 📚 Research & Advanced Workflows Skills Guide / 研究与高级工作流技能指南

## 📚 研究与高级工作流技能指南

> __Official Sources / 官方来源:__
> - planning-with-files: [OthmanAdi/planning-with-files](https://github.com/OthmanAdi/planning-with-files)
> - notebooklm-skill: [PleasePrompto/notebooklm-skill](https://github.com/PleasePrompto/notebooklm-skill)
>
> Please visit the official repositories for the most up-to-date information.
> 请访问官方仓库获取最新信息。

---

## 📋 Overview / 概述

Research and advanced workflow skills enable AI agents to maintain persistent context across sessions, perform intelligent document research, and manage complex knowledge-intensive tasks. These skills extend Claude Code's capabilities beyond single-session interactions.

研究和高级工作流技能使 AI 代理能够跨会话保持持久上下文、执行智能文档研究和管理复杂的知识密集型任务。这些技能扩展了 Claude Code 的能力，超越了单次交互的局限。

本指南涵盖了：
- **Advanced Planning / 高级规划** - File-based persistent knowledge management / 基于文件的持久化知识管理
- **AI-Powered Research / AI驱动的研究** - Intelligent document querying with NotebookLM / 使用 NotebookLM 进行智能文档查询

---

## 🗂️ Planning with Files / 文件规划

> __Quick Access / 快速访问:__ Use for complex tasks requiring 50+ tool calls / 用于需要 50+ 次工具调用的复杂任务

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像给 AI 配了一个"外置硬盘"当作工作记忆，所有重要的规划、发现、进度都持久化保存
**Like giving AI an "external hard drive" as working memory, with all important plans, findings, and progress persistently saved**

**能做什么 / Capabilities**:
- 防止目标漂移 / Prevent goal drift
- 追踪所有错误 / Track all errors
- 构建知识库 / Build knowledge base
- 跨会话保持上下文 / Maintain context across sessions

**什么时候用 / When to Use**:
- 复杂的多步骤任务（3+步骤）/ Complex multi-step tasks (3+ steps)
- 研究项目 / Research projects
- 需要 50+ 次工具调用的任务 / Tasks requiring 50+ tool calls
- 需要持久化知识的任务 / Tasks requiring persistent knowledge

**怎么用 / How to Use**:
```
告诉 Claude："开始这个复杂任务"
Tell Claude: "Start this complex task"

Claude 会自动创建三个文件：
Claude will automatically create three files:
- task_plan.md - 任务计划和进度
- findings.md - 研究发现
- progress.md - 会话日志
```

**举例 / Example**:
```
任务："构建一个完整的用户认证系统"

技能会：
1️⃣ 创建 task_plan.md
   - 阶段 1: 设计认证流程
   - 阶段 2: 实现 OAuth
   - 阶段 3: 添加 JWT 中间件
   - 阶段 4: 编写测试

2️⃣ 创建 findings.md
   - 研究：GitHub OAuth vs Google OAuth
   - 发现：推荐使用 JWT 而不是 Session

3️⃣ 创建 progress.md
   - 会话 1: 完成阶段 1-2
   - 会话 2: 完成阶段 3
   - 会话 3: 完成阶段 4

✅ 即使上下文重置，所有进度都保存在文件中！
```

### Purpose / 作用

Implement Manus AI's workflow pattern that uses persistent markdown files as "working memory on disk" to solve:

实现 Manus AI 的工作流模式，使用持久的 Markdown 文件作为"磁盘上的工作记忆"来解决：

- **Volatile memory / 易失性记忆** - TodoWrite tool disappears on context reset
  - TodoWrite 工具在上下文重置时消失
- **Goal drift / 目标漂移** - After 50+ tool calls, original goals get forgotten
  - 50+ 次工具调用后，原始目标被遗忘
- **Hidden errors / 隐藏错误** - Failures aren't tracked, same mistakes repeat
  - 失败未被追踪，同样错误重复出现
- **Context stuffing / 上下文填充** - Everything crammed into context instead of stored
  - 所有内容都塞入上下文而非存储

### Key Features / 主要特性

✨ **3-File Pattern / 3文件模式**
  - `task_plan.md` - Track phases and progress / 跟踪阶段和进度
  - `findings.md` - Store research and discoveries / 存储研究和发现
  - `progress.md` - Session log and test results / 会话日志和测试结果

✨ **Core Principle / 核心原则**
  ```
  Context Window = RAM (volatile, limited) / 上下文窗口 = RAM（易失、有限）
  Filesystem = Disk (persistent, unlimited) / 文件系统 = 磁盘（持久、无限）

  → Anything important gets written to disk / 任何重要内容都写入磁盘
  ```

✨ **Error Tracking / 错误追踪**
  - Log all errors to plan file / 将所有错误记录到计划文件
  - 3-Strike Error Protocol / 3次错误协议
  - Never repeat failures / 永不重复失败

✨ **Hooks Integration / Hooks 集成**
  - Auto-re-read plan before decisions / 在决策前自动重读计划
  - Verify completion on stop / 停止时验证完成度
  - Update progress automatically / 自动更新进度

### When to Use / 使用时机

**Use for / 适用于:**
- Multi-step tasks (3+ steps) / 多步骤任务（3+步骤）
- Research tasks / 研究任务
- Building/creating projects / 构建/创建项目
- Tasks spanning many tool calls / 跨越多次工具调用的任务
- Anything requiring organization / 任何需要组织的任务

**Skip for / 跳过:**
- Simple questions / 简单问题
- Single-file edits / 单文件编辑
- Quick lookups / 快速查询

### Critical Rules / 关键规则

1. **Create Plan First / 首先创建计划**
   Never start a complex task without `task_plan.md`. Non-negotiable.
   没有任务计划文件绝不开始复杂任务。不可协商。

2. **The 2-Action Rule / 2次操作规则**
   After every 2 view/browser/search operations, IMMEDIATELY save key findings to text files.
   每执行 2 次查看/浏览器/搜索操作后，立即将关键发现保存到文本文件。

3. **Read Before Decide / 决策前先读**
   Before major decisions, read the plan file. This keeps goals in your attention window.
   在做重大决策前，阅读计划文件。这会让目标保持在你的注意力窗口中。

4. **Update After Act / 操作后更新**
   After completing any phase:
   完成任何阶段后：
   - Mark phase status: `in_progress` → `complete`
   - Log any errors encountered
   - Note files created/modified

5. **Log ALL Errors / 记录所有错误**
   Every error goes in the plan file. This builds knowledge and prevents repetition.
   每个错误都写入计划文件。这建立知识库并防止重复。

### File Templates / 文件模板

#### task_plan.md
```markdown
# Task Plan: [任务名称]

## Goal / 目标
[清晰的目标描述]

## Phases / 阶段

### Phase 1: [阶段名称]
- [ ] Step 1.1
- [ ] Step 1.2
- [ ] Step 1.3

## Errors Encountered / 遇到的错误
| Error | Attempt | Resolution |
|-------|---------|------------|
| - | - | - |
```

#### findings.md
```markdown
# Findings / 研究发现

## Research / 研究
- [发现 1]
- [发现 2]

## Decisions / 决策
- [决策 1 及理由]
- [决策 2 及理由]
```

#### progress.md
```markdown
# Progress / 进度

## Session 1 - [日期]
- Completed Phase 1
- Started Phase 2
- Issues: [问题]
```

### Comparison with Existing Skills / 与现有技能的对比

| Feature | writing-plans | planning-with-files |
|---------|---------------|---------------------|
| Persistence | Temporary TodoWrite | Persistent files / 持久文件 |
| Scope | General planning | Complex tasks / 复杂任务 |
| Error Tracking | No | Yes (3-Strike Protocol) / 是（3次协议）|
| Context Management | In-context only | Filesystem as extended memory / 文件系统作为扩展记忆 |
| Best For | Simple tasks | Complex research/development / 复杂研究/开发 |

### Installation / 安装

```bash
# Clone to skills directory / 克隆到技能目录
cd ~/.claude/skills
git clone https://github.com/OthmanAdi/planning-with-files.git

# Or use plugin marketplace / 或使用插件市场
claude plugin marketplace add OthmanAdi/planning-with-files
claude plugin install planning-with-files@planning-with-files
```

### Resources / 资源

- **Original Repository / 原始仓库**: [github.com/OthmanAdi/planning-with-files](https://github.com/OthmanAdi/planning-with-files)
- **Inspiration / 灵感来源**: [Manus AI - Context Engineering](https://manus.im/blog/Context-Engineering-for-AI-Agents)
- **Author / 作者**: [@OthmanAdi](https://github.com/OthmanAdi)

---

## 🔍 NotebookLM / AI文档查询

> __Quick Access / 快速访问:__ Use when querying documentation or large document sets / 查询文档或大型文档集时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 让 Claude 直接和 Google NotebookLM 对话，基于你上传的文档获取智能答案，完全不瞎编
**Let Claude directly chat with Google NotebookLM to get intelligent answers based on your uploaded documents, without making things up**

**能做什么 / Capabilities**:
- 查询文档获取准确答案 / Query documents for accurate answers
- 减少幻觉（仅从文档回答）/ Reduce hallucinations (answers only from documents)
- 多文档关联分析 / Multi-document correlation analysis
- 自动跟进问题 / Automatic follow-up questions

**什么时候用 / When to Use**:
- 需要查询技术文档 / Need to query technical documentation
- 基于 API 文档写代码 / Write code based on API docs
- 研究大型 PDF 集合 / Research large PDF collections
- 需要源引用的答案 / Need source-cited answers

**怎么用 / How to Use**:
```
1. 上传文档到 NotebookLM
2. 分享 Notebook 链接
3. 告诉 Claude："查询这个 notebook 关于..."
```

**举例 / Example**:
```
任务："基于 React 文档实现一个自定义 Hook"

传统方法：
1. Claude 可能编造不存在的 API
2. 需要反复验证代码是否正确
3. 浪费时间在试错上

使用 NotebookLM 技能：
1. 已上传 React 文档到 NotebookLM
2. Claude: "问 React 文档关于自定义 Hook"
3. NotebookLM: "基于文档的准确答案 + 引用"
4. Claude: 基于真实 API 编写代码 ✅

结果：一次写对，没有幻觉！
```

### Purpose / 作用

Enable Claude Code to directly interact with Google NotebookLM for source-grounded answers based exclusively on your uploaded documents, solving:

让 Claude Code 直接与 Google NotebookLM 交互，基于你上传的文档获取源导向的答案，解决：

- **Massive token consumption / 巨大的 token 消耗** - Reading multiple files repeatedly
  - 反复读取多个文件
- **Inaccurate retrieval / 不准确的检索** - Keyword searches miss context and connections
  - 关键词搜索错过上下文和联系
- **Hallucinations / 幻觉** - When it can't find something, it invents plausible-sounding APIs
  - 找不到时，编造看似合理的 API
- **Manual copy-paste / 手动复制粘贴** - Switching between NotebookLM browser and editor
  - 在 NotebookLM 浏览器和编辑器之间切换

### Key Features / 主要特性

✨ **Source-Grounded Responses / 源导向响应**
  - Answers exclusively from uploaded documents / 仅从上传文档回答
  - Every answer includes source references / 每个答案包含源引用
  - Significantly reduces hallucinations / 显著减少幻觉

✨ **Direct Integration / 直接集成**
  - No copy-paste between browser and editor / 无需浏览器和编辑器间复制粘贴
  - Claude asks and receives answers programmatically / Claude 程序化询问并接收答案

✨ **Smart Library Management / 智能库管理**
  - Save NotebookLM links with tags and descriptions / 用标签和描述保存 NotebookLM 链接
  - Claude auto-selects the right notebook / Claude 自动选择正确的 notebook

✨ **Automatic Authentication / 自动认证**
  - One-time Google login / 一次 Google 登录
  - Authentication persists across sessions / 认证跨会话持久化

### Why NotebookLM vs Local RAG / 为什么选择 NotebookLM 而非本地 RAG？

| Approach | Token Cost | Setup Time | Hallucinations | Answer Quality |
|----------|------------|------------|----------------|----------------|
| Feed docs to Claude / 喂文档给 Claude | 🔴 Very high / 很高 | Instant / 即时 | Yes / 是 | Variable / 变化 |
| Web search / 网页搜索 | 🟡 Medium / 中等 | Instant / 即时 | High / 高 | Hit or miss / 不稳定 |
| Local RAG | 🟡 Medium-High / 中-高 | Hours / 小时 | Medium / 中等 | Depends / 取决于设置 |
| **NotebookLM Skill** | 🟢 Minimal / 最少 | 5 minutes / 5分钟 | **Minimal / 最少** | Expert / 专家级 |

### Core Workflow / 核心工作流

#### Step 1: Authentication / 认证（一次性）

```bash
# 设置 Google 认证
python scripts/run.py auth_manager.py setup
# 浏览器会打开，手动登录 Google
```

#### Step 2: Create Knowledge Base / 创建知识库

1. Go to [notebooklm.google.com](https://notebooklm.google.com)
2. Create notebook / 创建 notebook
3. Upload your docs / 上传文档：
   - PDFs, Google Docs, Markdown files
   - Websites, GitHub repos
   - YouTube videos
4. Share / 分享: ⚙️ Share → Anyone with link → Copy

#### Step 3: Add to Library / 添加到库

```bash
# 智能添加（推荐）
python scripts/run.py ask_question.py --question "What is the content of this notebook? What topics are covered?" --notebook-url "[URL]"

# 基于发现的内容添加
python scripts/run.py notebook_manager.py add --url "[URL]" --name "[发现的名称]" --description "[发现的内容]" --topics "[发现的主题]"
```

#### Step 4: Start Querying / 开始查询

```bash
# 查询特定 notebook
python scripts/run.py ask_question.py --question "How do I implement custom hooks?" --notebook-id "react-docs"
```

### Common Commands / 常用命令

| Command | What Happens |
|---------|--------------|
| *"Set up NotebookLM authentication"* | Opens Chrome for Google login |
| *"Add [link] to my NotebookLM library"* | Saves notebook with metadata |
| *"Show my NotebookLM notebooks"* | Lists all saved notebooks |
| *"Ask my API docs about [topic]"* | Queries the relevant notebook |
| *"Use the React notebook"* | Sets active notebook |
| *"Clear NotebookLM data"* | Fresh start (keeps library) |

### Real-World Examples / 真实案例

#### Example 1: Workshop Manual Query / 工作手册查询

```
User asks: "Check my Suzuki GSR 600 workshop manual for brake fluid type,
engine oil specs, and rear axle torque."

Claude automatically:
1. Authenticates with NotebookLM
2. Asks comprehensive questions about each specification
3. Provides accurate specifications:
   - DOT 4 brake fluid
   - SAE 10W-40 oil
   - 100 N·m rear axle torque
```

#### Example 2: Building Without Hallucinations / 无幻觉构建

```
You: "I need to build an n8n workflow for Gmail spam filtering. Use my n8n notebook."

Claude's internal process:
→ Loads NotebookLM skill
→ Activates n8n notebook
→ Asks comprehensive questions with follow-ups
→ Synthesizes complete answer from multiple queries

Result: Working workflow on first try, no debugging hallucinated APIs.
```

### When to Use / 使用时机

**Perfect for / 完美适用于:**
- Technical documentation queries / 技术文档查询
- API documentation research / API 文档研究
- Academic paper analysis / 学术论文分析
- Multi-document correlation / 多文档关联
- Source-cited answers needed / 需要源引用的答案

**Not ideal for / 不适用于:**
- Quick web searches / 快速网络搜索
- Real-time information / 实时信息
- General knowledge questions / 一般知识问题

### Limitations / 限制

- **Local Claude Code only / 仅限本地 Claude Code** - Does not work in web UI
  - 不在 Web UI 中工作
- **Rate limits / 速率限制** - Free tier has daily query limits
  - 免费版有每日查询限制
- **Manual upload required / 需要手动上传** - Must upload docs to NotebookLM first
  - 必须先上传文档到 NotebookLM
- **No session persistence / 无会话持久化** - Each question is independent
  - 每个问题都是独立的

### Installation / 安装

```bash
# Clone to skills directory / 克隆到技能目录
cd ~/.claude/skills
git clone https://github.com/PleasePrompto/notebooklm-skill.git notebooklm

# First use auto-sets up environment / 首次使用自动设置环境
# Creates .venv, installs dependencies, sets up Chrome
# 创建 .venv，安装依赖，设置 Chrome
```

### Comparison with Existing Skills / 与现有技能的对比

| Feature | PDF/DOCX Skills | notebooklm-skill |
|---------|----------------|------------------|
| Core Ability | **Format Processing** / 格式处理 | **Semantic Understanding** / 语义理解 |
| Use Case | Extract/convert content / 提取/转换内容 | Query and understand / 查询和理解 |
| AI Capability | None / 无 | Gemini 2.5 intelligent Q&A / 智能问答 |
| Output | Raw data / 原始数据 | Synthesized answers / 综合答案 |
| Hallucinations | N/A | Minimal (source-grounded) / 最少（源导向）|
| Best For | Format conversion / 格式转换 | Research and learning / 研究和学习 |

### Resources / 资源

- **Original Repository / 原始仓库**: [github.com/PleasePrompto/notebooklm-skill](https://github.com/PleasePrompto/notebooklm-skill)
- **MCP Server Version / MCP 服务器版本**: [github.com/PleasePrompto/notebooklm-mcp](https://github.com/PleasePrompto/notebooklm-mcp)
- **NotebookLM / NotebookLM**: [notebooklm.google.com](https://notebooklm.google.com)
- **Author / 作者**: [@PleasePrompto](https://github.com/PleasePrompto)

---

## 🎯 Skill Combinations / 技能组合

### Recommended Workflows / 推荐工作流

**1. Complex Research Project / 复杂研究项目**
```
planning-with-files (组织研究)
    +
notebooklm-skill (查询文档)
    +
systematic-debugging (解决问题)
```

**2. Large-Scale Development / 大规模开发**
```
brainstorming (构思)
    +
planning-with-files (持久规划)
    +
notebooklm-skill (查询技术文档)
    +
subagent-driven-development (执行开发)
```

**3. Documentation-Based Learning / 基于文档的学习**
```
notebooklm-skill (上传文档集)
    +
planning-with-files (记录学习进度)
    +
docx/pptx (生成学习笔记)
```

---

## 📊 Quick Comparison / 快速对比

| Skill | Best For / 最适用于 | Persistence / 持久性 | AI Power / AI 能力 |
|-------|---------------------|---------------------|-------------------|
| **planning-with-files** | Complex tasks / 复杂任务 | File-based / 文件系统 | Moderate / 中等 |
| **notebooklm-skill** | Document research / 文档研究 | Cloud / 云端 | High (Gemini 2.5) / 高 |

---

## 💡 Tips & Best Practices / 提示与最佳实践

### DO's / 推荐做法

✅ Use planning-with-files for any task spanning multiple sessions
✅ 对于跨多次会话的任务使用 planning-with-files

✅ Set up NotebookLM notebooks for frequently referenced documentation
✅ 为经常参考的文档设置 NotebookLM notebooks

✅ Always include descriptions when adding notebooks to library
✅ 添加 notebook 到库时总是包含描述

✅ Use the 2-Action Rule with planning-with-files
✅ 使用 planning-with-files 时遵循 2次操作规则

✅ Re-read plan files before major decisions
✅ 在重大决策前重读计划文件

### DON'Ts / 避免做法

❌ Don't use planning-with-files for simple single-step tasks
❌ 不要对简单的单步任务使用 planning-with-files

❌ Don't skip NotebookLM authentication setup
❌ 不要跳过 NotebookLM 认证设置

❌ Don't add notebooks without proper metadata
❌ 不要在没有适当元数据的情况下添加 notebooks

❌ Don't expect notebooklm-skill to work in web UI
❌ 不要期望 notebooklm-skill 在 Web UI 中工作

---

## 🔄 Migration from Other Skills / 从其他技能迁移

### From writing-plans to planning-with-files / 从 writing-plans 到 planning-with-files

```markdown
# Simple Task (use writing-plans) / 简单任务（使用 writing-plans）
Task: Add a button to the homepage
→ Use brainstorming → writing-plans → TDD

# Complex Task (use planning-with-files) / 复杂任务（使用 planning-with-files）
Task: Build complete authentication system
→ Use planning-with-files
  - task_plan.md (tracks all phases)
  - findings.md (research on OAuth vs JWT)
  - progress.md (logs across multiple sessions)
```

### From pdf to notebooklm-skill / 从 pdf 到 notebooklm-skill

```markdown
# Need to extract content (use pdf) / 需要提取内容（使用 pdf）
Task: Extract all tables from this 100-page PDF
→ Use pdf skill

# Need to understand and query (use notebooklm-skill) / 需要理解和查询（使用 notebooklm-skill）
Task: What does this 100-page PDF say about X? How does it relate to Y?
→ Upload to NotebookLM
→ Use notebooklm-skill for intelligent Q&A
```

---

__📚 Next: Check out [Software Development Skills](./01-software-development.md) for core development workflows.__

__📚 下一步：查看 [软件开发技能](./01-software-development.md) 了解核心开发工作流。__
