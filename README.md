# 🤖 Claude Skills Guide / Claude 技能指南

## 🤖 Claude 技能指南

__Comprehensive bilingual guide for Claude Code skills__

__Claude Code 技能的全面双语指南__

![GitHub repo size](https://img.shields.io/badge/skills-32-blue)
![GitHub language count](https://img.shields.io/badge/format-markdown-purple)
![GitHub last commit](https://img.shields.io/badge/status-complete-green)

---

## 📑 Table of Contents / 目录

**💡 提示 / Tip**: 每个技能在详细指南中都有通俗易懂的解释、使用场景和举例
**Each skill in detailed guides has simple explanations, use cases, and examples**

### 🎯 Software Development Skills / 软件开发技能（14个）
- 🧠 **Brainstorming** - Turn ideas into designs / 将想法转化为设计方案
- 📝 **Writing Plans** - Create implementation plans / 编写详细实施计划
- 🤖 **Subagent-Driven Development** - Fast iteration with two-stage review / 子代理驱动的开发流程
- 🧪 **Test-Driven Development** - RED-GREEN-REFACTOR cycle / 测试驱动开发
- ⚡ **Executing Plans** - Batch execution with checkpoints / 批量处理 + 检查点
- ✅ **Verification Before Completion** - Confirm bugs are fixed / 完成前验证
- 🎬 **Finishing Development Branch** - Merge/PR/discard workflow / 完成开发分支
- 👁️ **Requesting Code Review** - Pre-review checklist / 请求代码审查
- 📥 **Receiving Code Review** - Respond to feedback / 接收代码审查
- 🚀 **Dispatching Parallel Agents** - Concurrent problem solving / 调度并行子代理
- 🌳 **Using Git Worktrees** - Parallel development branches / 使用 Git Worktrees
- 🔍 **Systematic Debugging** - Structure debugging process / 系统化调试
- 📘 **Using Superpowers** - Skill usage guidelines / Superpowers 使用指南
- ✍️ **Writing Skills** - TDD for documentation / 编写技能

### 📄 Document Processing Skills / 文档处理技能（4个）
- 📕 **PDF** - Extract text, tables, images / PDF 文档处理
- 📗 **DOCX** - Read/write Word documents / Word 文档处理
- 📘 **PPTX** - Create PowerPoint presentations / PowerPoint 创建和编辑
- 📙 **XLSX** - Excel spreadsheet manipulation / Excel 电子表格处理

### 🌐 Web Development Skills / Web 开发技能（3个）
- 🧪 **WebApp Testing** - Playwright testing framework / Web 应用测试
- 🎨 **Web Artifacts Builder** - React + Tailwind HTML artifacts / Web 构件构建器
- 💻 **Frontend Design** - UI/UX design with React & Tailwind / 前端 UI/UX 设计

### 🎨 Visual & Media Skills / 视觉媒体技能（4个）
- 🎨 **Algorithmic Art** - Generative art creation / 算法艺术
- 🖼️ **Canvas Design** - HTML5 Canvas visual art / Canvas 视觉艺术
- 🎞️ **Slack GIF Creator** - Animated GIFs for Slack / Slack 优化的 GIF 动画
- 🎭 **Theme Factory** - 10 professional themes / 主题工厂（10个预设主题）

### 🔧 Tool Skills / 工具技能（5个）
- 🛠️ **Skill Creator** - Create new skills / 技能创建器
- 🔌 **MCP Builder** - Build Model Context Protocol servers / MCP 构建器
- 🤝 **Doc Coauthoring** - Collaborative document editing / 文档协作编辑
- 📢 **Internal Comms** - Company communication templates / 内部沟通模板
- 🎨 **Brand Guidelines** - Anthropic brand standards / Anthropic 品牌指南

### 📚 Research & Advanced Workflows Skills / 研究与高级工作流技能（2个）
- 🗂️ **Planning with Files** - Persistent file-based planning / 持久化文件规划
- 🔍 **NotebookLM** - AI-powered document research / AI 驱动的文档研究

---

## 🚀 Quick Start / 快速开始

### How Skills Work / 技能如何工作

1. **Automatic Triggering / 自动触发**
   - Claude Code detects task context
   - Claude Code 检测任务上下文
   - Automatically invokes relevant skills
   - 自动调用相关技能

2. **Manual Invocation / 手动调用**
   ```bash
   /skill-name
   /test-driven-development
   /brainstorming
   /pdf
   ```

3. **Skill Categories / 技能分类**
   - Development workflow (idea → plan → code → test → review → merge)
   - 开发工作流（创意→计划→代码→测试→审查→合并）
   - Document processing (PDF, Word, PowerPoint, Excel)
   - 文档处理（PDF、Word、PowerPoint、Excel）
   - Web development (design, build, test)
   - Web 开发（设计、构建、测试）
   - Visual creation (art, animation, themes)
   - 视觉创作（艺术、动画、主题）
   - Research & Advanced workflows (persistent planning, AI-powered research)
   - 研究与高级工作流（持久化规划、AI 驱动研究）

---

## 📊 Skills Overview / 技能概览

### Most Used Skills / 最常用技能

| Skill | Category | Trigger / 触发条件 |
|-------|----------|-------------------|
| **brainstorming** | Development | Any creative work / 任何创造性工作 |
| **test-driven-development** | Development | Writing code / 编写代码 |
| **systematic-debugging** | Development | Bug found / 发现 bug |
| **pdf** | Document | "Analyze PDF" / "分析 PDF" |
| **webapp-testing** | Web | "Test this app" / "测试这个应用" |

### Skill Dependencies / 技能依赖

Some skills require additional packages:
某些技能需要额外的包：

```bash
# Document processing / 文档处理
pip install pymupdf python-docx openpyxl python-pptx

# Visual media / 视觉媒体
pip install pillow imageio numpy

# Web testing / Web 测试
npm install -D @playwright/test
```

---

## 🎓 Learning Path / 学习路径

### For Developers / 面向开发者

1. **Start with / 从开始**:
   - brainstorming → writing-plans → test-driven-development
   - 头脑风暴 → 编写计划 → 测试驱动开发

2. **Then learn / 然后学习**:
   - systematic-debugging → verification-before-completion
   - 系统化调试 → 完成前验证

3. **Advanced / 进阶**:
   - subagent-driven-development → requesting-code-review
   - 子代理驱动开发 → 请求代码审查

### For Document Processing / 面向文档处理

1. **Start with / 从开始**:
   - pdf (most common / 最常用)

2. **Then learn / 然后学习**:
   - docx → pptx → xlsx

### For Web Development / 面向 Web 开发

1. **Start with / 从开始**:
   - frontend-design → web-artifacts-builder

2. **Then learn / 然后学习**:
   - webapp-testing

---

## 📖 Full Guides / 完整指南

**💡 每个技能都包含通俗易懂的解释、使用场景和举例**
**Each skill includes simple explanations, use cases, and examples**

### 🎯 [Software Development Skills (14)](./guides/01-software-development.md)
Complete workflow from idea to production / 从创意到生产的完整工作流

### 📄 [Document Processing Skills (4)](./guides/02-document-processing.md)
PDF, Word, PowerPoint, Excel / 处理PDF、Word、PowerPoint、Excel

### 🌐 [Web Development Skills (3)](./guides/03-web-development.md)
Design, build, test web apps / 设计、构建、测试Web应用

### 🎨 [Visual & Media Skills (4)](./guides/04-visual-media.md)
Art, animation, themes / 艺术、动画、主题

### 🔧 [Tool Skills (5)](./guides/05-tools.md)
Skills, MCP, collaboration / 技能、MCP、协作

### 📚 [Research & Advanced Workflows Skills (2)](./guides/06-research-and-advanced-workflows.md)
Persistent planning, AI-powered research / 持久化规划、AI 驱动研究

---

### 📚 [Quick Reference - 快速参考](./QUICK_REFERENCE_ALL_SKILLS.md)
所有32个技能的一页总览 / One-page overview of all 32 skills

---

## 💡 Tips & Best Practices / 提示与最佳实践

### DO's / 推荐做法

✅ Let Claude Code auto-detect which skill to use
✅ 让 Claude Code 自动检测使用哪个技能

✅ Read the skill guide before first use
✅ 第一次使用前阅读技能指南

✅ Combine multiple skills for complex workflows
✅ 组合多个技能处理复杂工作流

✅ Update skills regularly from GitHub
✅ 定期从 GitHub 更新技能

### DON'Ts / 避免做法

❌ Don't manually invoke skills when auto-detection works
❌ 自动检测有效时不要手动调用技能

❌ Don't skip code review skills in development workflow
❌ 不要在开发工作流中跳过代码审查技能

❌ Don't ignore skill prerequisites/dependencies
❌ 不要忽略技能的前提条件/依赖

---

## 🙏 Acknowledgments / 致谢

This guide is based on the amazing work from the following repositories:
本指南基于以下仓库的优秀工作：

### 📦 Source Repositories / 源仓库

#### 🎯 [obra/superpowers](https://github.com/obra/superpowers)
**Complete SDLC workflow skills / 完整SDLC工作流技能**

- Provides 14 skills for systematic software development
- 提供14个系统化软件开发技能
- Focus on quality-driven development with two-stage reviews
- 专注于质量驱动的开发和双阶段审查
- **Skills included / 包含技能**: brainstorming, writing-plans, subagent-driven-development, test-driven-development, systematic-debugging, code reviews, git worktrees, and more
- **Author**: [@obra](https://github.com/obra)

#### 🤖 [anthropics/skills](https://github.com/anthropics/skills)
**Official example skills by Anthropic / Anthropic 官方示例技能**

- Provides 16 skills for various use cases
- 提供16个不同使用场景的技能
- Covers document processing, web development, visual media, and tools
- 涵盖文档处理、Web开发、视觉媒体和工具
- **Skills included / 包含技能**: pdf, docx, pptx, xlsx, webapp-testing, frontend-design, algorithmic-art, slack-gif-creator, theme-factory, and more
- **Author**: [Anthropic](https://github.com/anthropics)

#### 🌟 [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills)
**Community-curated list of Claude skills / 社区策划的Claude技能列表**

- Comprehensive collection of Claude skills
- Claude技能的综合集合
- Curated resources and examples
- 策选的资源和示例
- **Maintainer**: [ComposioHQ](https://github.com/ComposioHQ)

---

## 🔗 Resources / 资源

### 📚 Original Reposories / 原始仓库
- 📖 [obra/superpowers](https://github.com/obra/superpowers) - Systematic development workflow
- 📖 [anthropics/skills](https://github.com/anthropics/skills) - Official example skills
- 📖 [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) - Community collection

### 📖 Documentation / 文档
- 📖 [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- 📖 [Claude Documentation](https://docs.anthropic.com/claude)

---

---

## 📝 Changelog / 更新日志

| Date | Changes / 更改 |
|------|---------------|
| 2025-01-13 | Initial deployment of 30 skills / 30 个技能的初始部署 |
| 2025-01-13 | Created comprehensive bilingual guides / 创建全面的双语指南 |
| 2025-01-13 | Added Research & Advanced Workflows skills (2) / 添加研究与高级工作流技能（2个） |

---

__Made with ❤️ for Claude Code users by Yifo98__

---

_💡 Tip: Press `Home` or `Ctrl + Home` to scroll back to top / 按 `Home` 或 `Ctrl + Home` 返回顶部_

_💡 Tip: Click on skill names or guide links to access full documentation / 点击技能名称或指南链接访问完整文档_
