# 🔧 Tool Skills Guide / 工具技能指南

## 🔧 工具技能指南

> __Official Sources / 官方来源:__
> Based on anthropics/skills and obra/superpowers repositories
> 基于 anthropics/skills 和 obra/superpowers 仓库

---

## 📋 Overview / 概述

Tool skills provide utilities for creating skills, building MCP servers, collaborating on documents, internal communications, and brand guidelines.

工具技能提供创建技能、构建 MCP 服务器、文档协作、内部沟通和品牌指南的实用工具。

本指南涵盖了：
- **Skill Creator / 技能创建器** - Create new Claude skills / 创建新的 Claude 技能
- **MCP Builder / MCP 构建器** - Build Model Context Protocol servers / 构建 MCP 服务器
- **Doc Coauthoring / 文档协作** - Collaborative document editing / 协作文档编辑
- **Internal Comms / 内部沟通** - Company communication templates / 公司沟通模板
- **Brand Guidelines / 品牌指南** - Anthropic brand standards / Anthropic 品牌标准

---

## 🛠️ Skill Creator / 技能创建器

> __Quick Access / 快速访问:__ Use when creating new skills / 创建新技能时使用

### Purpose / 作用

Create new Claude Code skills with proper structure:
创建具有正确结构的新 Claude Code 技能：

- Skill file structure
  - 技能文件结构
- YAML frontmatter
  - YAML 前置元数据
- Documentation format
  - 文档格式
- Testing and validation
  - 测试和验证

### Key Features / 主要特性

✨ **Skill Structure / 技能结构**
```yaml
---
name: skill-name
description: What this skill does
---

# Skill Title

## Overview
Description of the skill

## Quick Start
How to use it

## Key Features
Main capabilities

## Best Practices
Recommendations
```

✨ **Creation Process / 创建流程**
  1. Define skill purpose
  2. Create SKILL.md with frontmatter
  3. Write documentation
  4. Add examples
  5. Test skill
  6. Deploy to skills directory

### Example / 示例

```markdown
---
name: data-analysis
description: Use when analyzing datasets, creating visualizations, or performing statistical operations
---

# Data Analysis

## Overview
Perform comprehensive data analysis with Python.

## Quick Start
```python
import pandas as pd
import matplotlib.pyplot as plt

# Load data
df = pd.read_csv('data.csv')

# Analyze
summary = df.describe()
print(summary)

# Visualize
df.plot(kind='bar')
plt.show()
```

## Key Features
- Load various data formats
- Statistical analysis
- Data visualization
- Export reports
```

### Best Practices / 最佳实践

✅ Write clear descriptions / 编写清晰的描述
✅ Include practical examples / 包含实用示例
✅ Test before deploying / 部署前测试
❌ Don't create overly specific skills / 不要创建过于具体的技能

---

## 🔌 MCP Builder / MCP 构建器

> __Quick Access / 快速访问:__ Use when building MCP servers / 构建 MCP 服务器时使用

### Purpose / 作用

Build Model Context Protocol (MCP) servers:
构建模型上下文协议 (MCP) 服务器：

- Connect external tools to Claude
  - 将外部工具连接到 Claude
- Resource and tool definitions
  - 资源和工具定义
- Server implementation
  - 服务器实现

### Key Features / 主要特性

✨ **MCP Concepts / MCP 概念**
  - **Resources / 资源**: Data exposed to Claude
  - **Tools / 工具**: Functions Claude can call
  - **Prompts / 提示**: Reusable prompt templates

✨ **Server Structure / 服务器结构**
```python
from mcp.server import Server
from mcp.types import Tool, Resource

app = Server("my-mcp-server")

@app.tool()
async def my_tool(param: str) -> str:
    """Tool description"""
    return f"Result: {param}"

@app.resource("data://{id}")
async def get_data(id: str) -> str:
    """Get data by ID"""
    return f"Data for {id}"
```

### Example / 示例

```python
# mcp_server.py
from mcp.server import Server
from mcp.types import Tool, TextContent
import sqlite3

app = Server("database-mcp")

@app.tool()
async def query_database(sql: str) -> str:
    """Execute SQL query on database"""
    conn = sqlite3.connect('mydb.db')
    cursor = conn.cursor()
    cursor.execute(sql)
    results = cursor.fetchall()
    conn.close()
    return str(results)

@app.resource("db://tables")
async def list_tables() -> str:
    """List all tables"""
    # Implementation
    return "tables: users, orders, products"
```

### Best Practices / 最佳实践

✅ Validate all inputs / 验证所有输入
✅ Handle errors gracefully / 优雅地处理错误
✅ Provide clear descriptions / 提供清晰的描述
❌ Don't expose sensitive operations / 不要暴露敏感操作

---

## 🤝 Doc Coauthoring / 文档协作

> __Quick Access / 快速访问:__ Use when collaborating on documents / 协作文档时使用

### Purpose / 作用

Enable collaborative document editing:
启用协作文档编辑：

- Track changes
  - 跟踪更改
- Multiple contributors
  - 多个贡献者
- Version control
  - 版本控制
- Review and approval
  - 审查和批准

### Key Features / 主要特性

✨ **Collaboration Features / 协作功能**
  - Comment on specific sections
  - 对特定部分评论
  - Suggest edits
  - 建议编辑
  - Resolve conflicts
  - 解决冲突

✨ **Workflow / 工作流**
  1. Create document
  2. Share with collaborators
  3. Collect feedback
  4. Review and incorporate
  5. Finalize and publish

### Example / 示例

```markdown
# Project Proposal

## Overview
This project aims to...

<!-- @alice: Please review the timeline -->
## Timeline
- Phase 1: 2 weeks
- Phase 2: 3 weeks
- <!-- @bob: Need clarification here --> Phase 3: TBD

## Budget
Total: $50,000

## Comments
- @alice: Timeline looks good
- @bob: I'll update Phase 3 by Friday
```

### Best Practices / 最佳实践

✅ Use clear comment syntax / 使用清晰的注释语法
✅ Tag specific contributors / 标记特定贡献者
✅ Resolve conflicts promptly / 及时解决冲突
❌ Don't ignore feedback / 不要忽略反馈

---

## 📢 Internal Comms / 内部沟通

> __Quick Access / 快速访问:__ Use for company communications / 公司沟通时使用

### Purpose / 作用

Create professional internal communications:
创建专业的内部沟通：

- Announcements
  - 公告
- Updates
  - 更新
- Reports
  - 报告
- Meeting notes
  - 会议记录

### Key Features / 主要特性

✨ **Communication Types / 沟通类型**
  - **Announcements / 公告**: Company-wide updates
  - **Project Updates / 项目更新**: Progress reports
  - **Meeting Notes / 会议记录**: Decision summaries
  - **Action Items / 行动项**: Next steps

✨ **Templates / 模板**

**Announcement / 公告**
```
Subject: [Topic] Announcement

Hi team,

I'm writing to announce...

Key points:
- Point 1
- Point 2

Action required: [Yes/No]

Next steps:...

Questions? Contact [name]
```

**Project Update / 项目更新**
```
Project: [Name]
Status: [On Track/At Risk/Complete]
Period: [Date range]

Accomplishments:
- ✅ Item 1
- ✅ Item 2

Upcoming:
- 🔄 Item 3
- 🔄 Item 4

Blockers:
- 🚧 Blocker 1 - Owner: Name
```

### Best Practices / 最佳实践

✅ Be clear and concise / 清晰简洁
✅ Include action items / 包含行动项
✅ Provide context / 提供上下文
❌ Don't use jargon excessively / 不要过度使用行话

---

## 🎨 Brand Guidelines / 品牌指南

> __Quick Access / 快速访问:__ Use when creating branded content / 创建品牌内容时使用

### Purpose / 作用

Apply Anthropic brand standards correctly:
正确应用 Anthropic 品牌标准：

- Colors
  - 颜色
- Typography
  - 字体
- Logo usage
  - 标志使用
- Voice and tone
  - 语气和语调

### Key Features / 主要特性

✨ **Brand Colors / 品牌颜色**

**Primary Colors / 主色调**
```css
--anthropic-blue: #4A6FA5;
--anthropic-dark: #1E293B;
--anthropic-light: #F8FAFC;
```

**Accent Colors / 强调色**
```css
--anthropic-teal: #14B8A6;
--anthropic-purple: #8B5CF6;
```

✨ **Typography / 字体**

**Headings / 标题**
- Font: Inter, SF Pro Display
- Weight: 600-700
- Line height: 1.2

**Body / 正文**
- Font: Inter, system-ui
- Weight: 400-500
- Line height: 1.6

✨ **Voice and Tone / 语气和语调**
- Professional but approachable
- Clear and concise
- Helpful and informative
- Avoid overly technical jargon

### Example / 示例

```html
<!-- Branded component -->
<div class="anthropic-brand">
  <h1>Welcome to Claude</h1>
  <p>Your AI assistant for...</p>

  <button class="btn-primary">
    Get Started
  </button>
</div>

<style>
.anthropic-brand {
  font-family: 'Inter', system-ui, sans-serif;
  color: #1E293B;
  background: #F8FAFC;
}

.anthropic-brand h1 {
  font-weight: 700;
  color: #4A6FA5;
  font-size: 2.5rem;
  line-height: 1.2;
}

.anthropic-brand p {
  font-weight: 400;
  line-height: 1.6;
  color: #475569;
}

.btn-primary {
  background: #4A6FA5;
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  font-weight: 600;
  transition: background 0.2s;
}

.btn-primary:hover {
  background: #3B5998;
}
</style>
```

### Best Practices / 最佳实践

✅ Use correct colors / 使用正确的颜色
✅ Follow typography guidelines / 遵循字体指南
✅ Maintain consistent voice / 保持一致的语气
❌ Don't modify logo proportions / 不要修改标志比例
❌ Don't use unapproved colors / 不要使用未批准的颜色

---

## 📊 Summary / 总结

### Tool Usage Workflow / 工具使用工作流

```
Create Skill → Test Skill → Deploy Skill → Build MCP → Document → Communicate
     ↓            ↓           ↓            ↓          ↓          ↓
    Define      Validate    Install    Connect    Collab    Share
    Purpose     Function    to Claude  Tools      Editing   Updates
```

### Key Principles / 关键原则

✨ **Extensibility / 可扩展性**
  - Create reusable skills
  - 创建可重用技能
  - Build custom tools
  - 构建自定义工具

✨ **Collaboration / 协作**
  - Work together effectively
  - 有效地协同工作
  - Share knowledge
  - 分享知识

✨ **Consistency / 一致性**
  - Follow brand guidelines
  - 遵循品牌指南
  - Maintain standards
  - 维护标准

---

## 🔗 Resources / 资源

- 📖 [MCP Documentation](https://modelcontextprotocol.io/)
- 📖 [Anthropic Brand Guidelines](https://www.anthropic.com/brand)
- 📖 [Claude Code Skills Guide](https://github.com/anthropics/skills)

---

_💡 Tip: Combine tool skills with other categories for complete workflows / 提示：将工具技能与其他类别组合以实现完整工作流_
