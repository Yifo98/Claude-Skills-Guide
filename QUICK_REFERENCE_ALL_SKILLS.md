# 🚀 Claude Skills 快速参考 / Quick Reference

## 📑 目录导航 / Table of Contents

<details>
<summary><strong>📖 点击展开目录 / Click to Expand</strong></summary>

### 🎯 按类别浏览 / Browse by Category
- [📂 软件开发技能（14个）](#-软件开发技能14个-software-development-14)
- [📄 文档处理技能（4个）](#-文档处理技能4个-document-processing-4)
- [🌐 Web开发技能（3个）](#-web开发技能3个-web-development-3)
- [🎨 视觉媒体技能（4个）](#-视觉媒体技能4个-visual--media-4)
- [📚 研究与高级工作流技能（2个）](#-研究与高级工作流技能2个-research--advanced-workflows-2)
- [🔧 工具技能（5个）](#-工具技能5个-tools-5)

### 🎯 按用途查找 / Find by Purpose
- [📊 使用场景总览](#-使用场景总览-usage-scenarios-overview)
- [💡 快速查找指南](#-快速查找指南-quick-find-guide)
- [🎯 技能组合建议](#-技能组合建议-skill-combinations)

</details>

---

## 🎯 所有51个技能通俗解释 / All Skills Explained Simply

---

## 📂 软件开发技能（14个） / Software Development (14)

<details>
<summary><strong>📖 点击展开/折叠 / Click to Expand/Collapse</strong></summary>

### 🧠 Brainstorming / 头脑风暴

**是什么 / What**:
像和产品经理聊天一样，把你的模糊想法变成清晰的设计方案

**能做什么 / Capabilities**:
- 问你问题搞清楚需求
- 看看现有代码怎么做
- 探索几种技术方案
- 设计出实施方案

**什么时候用 / When to Use**:
- 要加新功能时
- 要改现有功能时
- 要从头设计时
- 不确定怎么做时

**怎么用 / How to Use**:
```
直接告诉 Claude 你的想法，技能会自动启动
例如："我想加个用户登录功能"
Claude 会自动调用 brainstorming 技能
```

**举例 / Example**:
```
你说："我想加个用户登录功能"
技能会：
1️⃣ 先看你的项目现在啥样
2️⃣ 问：用什么方式登录？（GitHub？Google？邮箱？）
3️⃣ 问：要存哪些用户数据？
4️⃣ 问：有没有现成的认证系统？
5️⃣ 给你设计一个完整的登录方案

就像有个经验丰富的产品经理帮你梳理思路！
```

---

### 📝 Writing Plans / 编写计划

**是什么 / What**:
像项目经理写任务清单，把大任务拆成一个个小步骤

**能做什么 / Capabilities**:
- 把大功能拆成小任务
- 定义每个任务的完成标准
- 找出任务之间的依赖关系
- 让任务可以并行执行

**什么时候用 / When to Use**:
- 头脑风暴结束后
- 要开始写代码前
- 项目比较复杂时
- 需要多人协作时

**怎么用 / How to Use**:
```
完成头脑风暴后，告诉 Claude："帮我写个实施计划"
Claude 会自动调用 writing-plans 技能
创建详细的任务清单
```

**举例 / Example**:
```
任务："实现用户认证"

拆成的计划：
☐ 任务1：创建OAuth控制器
   成功标准：POST /auth/github 返回token
☐ 任务2：添加JWT中间件
   成功标准：受保护路由需要有效token
☐ 任务3：创建用户数据模型
   成功标准：用户可以保存和读取
☐ 任务4：写集成测试
   成功标准：所有测试通过

每一步都清晰可见，做完打勾就行！
```

---

### 🤖 Subagent-Driven Development / 子代理驱动开发

**是什么 / What**:
像有个开发助手团队，每个任务派个新助手来做，做完了还要双重检查

**能做什么 / Capabilities**:
- 每个任务用全新的助手
- 两次代码审查（符合计划+代码质量）
- 在问题变大前发现它
- 快速迭代开发

**什么时候用 / When to Use**:
- 要执行开发计划时
- 需要快速开发时
- 项目比较复杂时
- 想保证质量时

**怎么用 / How to Use**:
```
当有书面计划时，告诉 Claude："执行这个计划"
Claude 会自动使用 subagent-driven-development
为每个任务分配新的子代理，并进行双重审查
```

---

### 🧪 Test-Driven Development / 测试驱动开发

**是什么 / What**:
先写测试（失败）→ 写代码（通过）→ 优化代码，三步循环

**能做什么 / Capabilities**:
- 确保代码真的能工作
- 防止改代码时搞坏功能
- 让代码更容易维护
- 提供代码使用示例

**什么时候用 / When to Use**:
- 写任何功能代码时
- 修bug时
- 重构代码时
- 基本上任何时候都要写代码

**怎么用 / How to Use**:
```
写代码时，Claude 会自动使用 TDD 流程：
1. 先写失败的测试
2. 写最小代码让测试通过
3. 重构优化代码
```

---

### ⚡ Executing Plans / 执行计划

**是什么 / What**:
像批量处理任务，每做完3个任务就停下来检查一下

**能做什么 / Capabilities**:
- 批量执行任务
- 定期检查进度
- 发现问题及时调整
- 跟踪整体进度

**什么时候用 / When to Use**:
- 有书面计划时
- 任务比较多时
- 需要定期检查时
- 长时间开发时

**怎么用 / How to Use**:
```
告诉 Claude："按计划执行这些任务"
Claude 会自动使用 executing-plans 技能
每3个任务进行一次代码审查检查点
```

---

### ✅ Verification Before Completion / 完成前验证

**是什么 / What**:
关闭bug或任务前，先验证一下真的修好了吗

**能做什么 / Capabilities**:
- 测试修复是否有效
- 验证根本原因已解决
- 检查有没有副作用
- 防止过早关闭问题

**什么时候用 / When to Use**:
- 修完bug后
- 完成任务后
- 关闭issue前
- 任何时候声称"搞定了"

**怎么用 / How to Use**:
```
完成任务后，告诉 Claude："验证一下这个真的修好了吗"
Claude 会自动使用 verification-before-completion
进行系统化验证
```

---

### 🎬 Finishing Development Branch / 完成开发分支

**是什么 / What**:
功能做完了，要合并到主分支了，有三种处理方式

**能做什么 / Capabilities**:
- 直接合并（简单改动）
- 创建PR（需要审查）
- 丢弃分支（实验失败）

**什么时候用 / When to Use**:
- 功能开发完成时
- 准备合并代码时
- 实验不需要时
- 分支太乱需要清理时

**怎么用 / How to Use**:
```
告诉 Claude："这个分支做完了，怎么处理？"
Claude 会使用 finishing-a-development-branch
帮你选择最合适的结束方式
```

---

### 👁️ Requesting Code Review / 请求代码审查

**是什么 / What**:
写完代码后，请别人（或另一个AI）帮你检查一下有什么问题

**能做什么 / Capabilities**:
- 系统化的代码审查
- 两阶段检查（符合计划+代码质量）
- 在问题变严重前发现
- 获取改进建议

**什么时候用 / When to Use**:
- 完成任务后
- 完成功能后
- 合并代码前
- 被卡住时

**怎么用 / How to Use**:
```
完成任务后，告诉 Claude："帮我审查一下这段代码"
Claude 会自动调用 requesting-code-review
进行系统化的代码审查
```

---

### 📥 Receiving Code Review / 接收代码审查

**是什么 / What**:
别人审查你的代码提意见了，你要建设性地回应

**能做什么 / Capabilities**:
- 技术性评价（不是盲目同意）
- 错的时候可以反驳
- 对的时候学习改进
- 保持专业态度

**什么时候用 / When to Use**:
- 收到代码审查反馈后
- 需要回应建议时
- 不确定建议是否正确时
- 需要讨论技术方案时

---

### 🚀 Dispatching Parallel Agents / 调度并行子代理

**是什么 / What**:
同时派几个AI助手分别解决同一个问题，然后比较结果选最好的

**能做什么 / Capabilities**:
- 并发解决问题
- 获得不同视角
- 探索多种方案
- 更快迭代

**什么时候用 / When to Use**:
- 有多个独立问题时
- 需要探索方案时
- 不确定哪种方法好时
- 需要新思路时

---

### 🌳 Using Git Worktrees / 使用Git Worktrees

**是什么 / What**:
同一个仓库可以有好几个工作目录，同时在不同分支上工作

**能做什么 / Capabilities**:
- 同时开发多个功能
- 热修复时不打断功能开发
- 轻松切换上下文
- 避免频繁 stash/pop

**什么时候用 / When to Use**:
- 同时做多件事时
- 紧急修复时
- 测试不同方案时
- 审查代码时还在开发

---

### 🔍 Systematic Debugging / 系统化调试

**是什么 / What**:
有条理地排查bug，而不是瞎改代码碰运气

**能做什么 / Capabilities**:
- 系统化调查问题
- 找到根本原因
- 验证假设
- 记录发现

**什么时候用 / When to Use**:
- 发现bug时
- 不知道怎么修时
- bug很复杂时
- 需要理解问题时

**怎么用 / How to Use**:
```
遇到bug时，告诉 Claude："帮我系统化地调试这个问题"
Claude 会使用 systematic-debugging
有条理地排查问题
```

---

### 📘 Using Superpowers / Superpowers使用指南

**是什么 / What**:
教你怎么用这些技能的说明书

**能做什么 / Capabilities**:
- 技能调用规则
- 危险信号警示
- 最佳实践建议
- 完整工作流程

**什么时候用 / When to Use**:
- 第一次使用技能时
- 不清楚用哪个技能时
- 想了解最佳实践时
- 遇到问题时

---

### ✍️ Writing Skills / 编写技能

**是什么 / What**:
用TDD的方法来写技能文档，先测试再写文档

**能做什么 / Capabilities**:
- 先用再写
- 真实场景验证
- 迭代改进文档
- 确保文档准确

**什么时候用 / When to Use**:
- 创建新技能时
- 改进现有技能时
- 技能文档过时时
- 分享技能给他人时

</details>

[⬆️ 回到顶部 / Back to Top](#-claude-skills-快速参考--quick-reference)

---

## 📄 文档处理技能（4个） / Document Processing (4)

<details>
<summary><strong>📖 点击展开/折叠 / Click to Expand/Collapse</strong></summary>

### 📕 PDF / PDF文档处理

**是什么 / What**:
从PDF提取内容（文本、表格、图像）

**能做什么 / Capabilities**:
- 提取文本并保留格式
- 解析复杂表格
- 提取所有图像
- OCR识别扫描文档

**什么时候用 / When to Use**:
- 分析PDF文档时
- 解析发票和收据
- 分析学术论文
- PDF转文本

**怎么用 / How to Use**:
```
告诉 Claude："分析这个PDF文件"
Claude 会使用 pdf 技能提取和处理内容
```

---

### 📗 DOCX / Word文档处理

**是什么 / What**:
创建和编辑Word文档

**能做什么 / Capabilities**:
- 创建程序化文档
- 读写现有文档
- 修改内容和格式
- 添加表格和图像

**什么时候用 / When to Use**:
- 自动生成报告时
- 创建发票时
- 填充模板时
- 文档邮件合并时

**怎么用 / How to Use**:
```
告诉 Claude："帮我生成一个Word文档"
Claude 会使用 docx 技能创建文档
```

---

### 📘 PPTX / PowerPoint创建编辑

**是什么 / What**:
创建PowerPoint演示文稿

**能做什么 / Capabilities**:
- 创建幻灯片
- 添加内容和形状
- 插入图像和图表
- 应用主题和动画

**什么时候用 / When to Use**:
- 自动生成报告时
- 制作培训材料时
- 数据可视化演示时
- 基于模板生成时

**怎么用 / How to Use**:
```
告诉 Claude："制作一个PowerPoint演示"
Claude 会使用 pptx 技能创建演示文稿
```

---

### 📙 XLSX / Excel电子表格处理

**是什么 / What**:
操作Excel（公式、图表、数据）

**能做什么 / Capabilities**:
- 读写Excel文件
- 添加公式和函数
- 创建图表
- 应用格式和样式

**什么时候用 / When to Use**:
- 财务报告时
- 数据分析时
- 发票生成时
- 数据导入导出时

**怎么用 / How to Use**:
```
告诉 Claude："帮我生成一个Excel报表"
Claude 会使用 xlsx 技能处理电子表格
```

</details>

[⬆️ 回到顶部 / Back to Top](#-claude-skills-快速参考--quick-reference)

---

## 🌐 Web开发技能（3个） / Web Development (3)

<details>
<summary><strong>📖 点击展开/折叠 / Click to Expand/Collapse</strong></summary>

### 💻 Frontend Design / 前端UI/UX设计

**是什么 / What**:
用React和Tailwind CSS设计现代界面

**能做什么 / Capabilities**:
- 组件化设计
- 响应式布局
- 现代样式系统
- TypeScript支持

**什么时候用 / When to Use**:
- 设计UI/UX时
- 创建组件时
- 重构界面时
- 优化用户体验时

**怎么用 / How to Use**:
```
告诉 Claude："帮我设计这个页面"
Claude 会使用 frontend-design 技能
创建 React + Tailwind 组件
```

---

### 🎨 Web Artifacts Builder / Web构件构建器

**是什么 / What**:
用React+Tailwind创建精美HTML构件

**能做什么 / Capabilities**:
- React组件开发
- Tailwind样式
- Vite构建工具
- 生产就绪的构建

**什么时候用 / When to Use**:
- 创建HTML构件时
- 快速开发时
- 优化构建时
- 部署到生产时

**怎么用 / How to Use**:
```
告诉 Claude："创建一个Web构件"
Claude 会使用 web-artifacts-builder 技能
创建完整的HTML构件项目
```

---

### 🧪 WebApp Testing / Web应用测试

**是什么 / What**:
用Playwright测试Web应用

**能做什么 / Capabilities**:
- 自动化测试
- 跨浏览器支持
- 视觉回归测试
- 并发执行

**什么时候用 / When to Use**:
- 测试Web应用时
- 验证功能时
- 回归测试时
- 质量保证时

**怎么用 / How to Use**:
```
告诉 Claude："测试这个Web应用"
Claude 会使用 webapp-testing 技能
编写Playwright测试
```

</details>

[⬆️ 回到顶部 / Back to Top](#-claude-skills-快速参考--quick-reference)

---

## 🎨 视觉媒体技能（4个） / Visual & Media (4)

<details>
<summary><strong>📖 点击展开/折叠 / Click to Expand/Collapse</strong></summary>

### 🎨 Algorithmic Art / 算法艺术

**是什么 / What**:
用算法和数学模式创建艺术

**能做什么 / Capabilities**:
- 程序化生成
- 数学模式
- Perlin噪声
- 粒子系统

**什么时候用 / When to Use**:
- 创建生成艺术时
- 实验视觉效果时
- 设计图案时
- 探索算法美学时

**怎么用 / How to Use**:
```
告诉 Claude："创建一些算法艺术"
Claude 会使用 algorithmic-art 技能
生成艺术作品
```

---

### 🖼️ Canvas Design / Canvas视觉艺术

**是什么 / What**:
用HTML5 Canvas创建视觉艺术

**能做什么 / Capabilities**:
- 交互式图形
- 动画效果
- 复杂可视化
- 实时渲染

**什么时候用 / When to Use**:
- 创建Canvas艺术时
- 制作动画效果时
- 数据可视化时
- 实时渲染时

**怎么用 / How to Use**:
```
告诉 Claude："用Canvas创建视觉效果"
Claude 会使用 canvas-design 技能
创建Canvas艺术
```

---

### 🎞️ Slack GIF Creator / Slack GIF创建器

**是什么 / What**:
创建为Slack优化的动画GIF

**能做什么 / Capabilities**:
- 适当尺寸（128x128 emoji）
- 优化文件大小
- 流畅动画（10-30fps）
- 短持续时间（<3秒）

**什么时候用 / When to Use**:
- 创建Slack emoji时
- 制作团队GIF时
- 优化动画文件时
- 团队文化建设时

**怎么用 / How to Use**:
```
告诉 Claude："创建一个Slack GIF"
Claude 会使用 slack-gif-creator 技能
生成优化的GIF动画
```

---

### 🎭 Theme Factory / 主题工厂

**是什么 / What**:
应用10个专业主题到内容

**能做什么 / Capabilities**:
- 北极霜（冷蓝白色）
- 植物园（绿色土色）
- 沙漠玫瑰（暖橙红色）
- 森林树冠（深绿棕色）
- 黄金时刻（暖黄琥珀色）
- 午夜银河（深蓝紫色）
- 现代极简（灰色黑色）
- 海洋深处（深蓝青色）
- 日落大道（鲜艳橙粉色）
- 科技创新（蓝青色）

**什么时候用 / When to Use**:
- 应用主题时
- 设计一致性时
- 专业外观时
- 品牌建设时

**怎么用 / How to Use**:
```
告诉 Claude："应用午夜银河主题"
Claude 会使用 theme-factory 技能
应用专业主题样式
```

</details>

[⬆️ 回到顶部 / Back to Top](#-claude-skills-快速参考--quick-reference)

---

## 📚 研究与高级工作流技能（2个） / Research & Advanced Workflows (2)

<details>
<summary><strong>📖 点击展开/折叠 / Click to Expand/Collapse</strong></summary>

### 🗂️ Planning with Files / 文件规划

**是什么 / What**:
像给 AI 配了个"外置硬盘"当作工作记忆，所有重要的规划、发现、进度都持久化保存

**能做什么 / Capabilities**:
- 防止目标漂移（50+工具调用后目标仍在）
- 追踪所有错误（永不重复失败）
- 构建知识库（研究发现的持久化存储）
- 跨会话保持上下文（文件系统作为扩展记忆）

**什么时候用 / When to Use**:
- 复杂的多步骤任务（3+步骤）
- 研究项目（需要积累知识）
- 需要 50+ 次工具调用的任务
- 跨多次会话的长时间任务

**怎么用 / How to Use**:
```
告诉 Claude："开始这个复杂任务"
Claude 会自动创建三个文件：
- task_plan.md - 任务计划和进度
- findings.md - 研究发现
- progress.md - 会话日志
```

**举例 / Example**:
```
任务："构建完整的用户认证系统"

技能会：
1️⃣ 创建 task_plan.md
   - 阶段 1-4，每个阶段多个步骤
   - 进度复选框
   - 错误追踪表格

2️⃣ 创建 findings.md
   - OAuth vs JWT 研究结论
   - 技术决策记录
   - 重要发现存档

3️⃣ 创建 progress.md
   - 每次会话的日志
   - 测试结果记录

✅ 即使上下文重置，所有进度都在文件中！
```

**关键规则**:
1. 创建计划文件：开始复杂任务前必须创建 task_plan.md
2. 2次操作规则：每 2 次查看/搜索操作后立即保存发现
3. 决策前重读：重大决策前重读计划文件
4. 记录所有错误：每个错误都记录，防止重复

---

### 🔍 NotebookLM / AI文档查询

**是什么 / What**:
让 Claude 直接和 Google NotebookLM 对话，基于你上传的文档获取智能答案，完全不瞎编

**能做什么 / Capabilities**:
- 查询文档获取准确答案（基于源材料）
- 减少幻觉（仅从上传文档回答）
- 多文档关联分析（连接 50+ 文档的信息）
- 自动跟进问题（确保信息完整）

**什么时候用 / When to Use**:
- 需要查询技术文档（如 React 文档、API 文档）
- 基于 API 文档写代码（避免幻觉）
- 研究大型 PDF 集合（学术论文、技术手册）
- 需要源引用的答案

**怎么用 / How to Use**:
```
1. 上传文档到 NotebookLM (notebooklm.google.com)
2. 分享 Notebook 链接
3. 告诉 Claude："查询这个 notebook 关于..."
```

**举例 / Example**:
```
任务："基于 React 文档实现自定义 Hook"

传统方法：
❌ Claude 可能编造不存在的 API
❌ 需要反复验证代码
❌ 浪费时间试错

使用 NotebookLM 技能：
✅ 已上传 React 文档到 NotebookLM
✅ Claude: "问 React 文档关于自定义 Hook"
✅ NotebookLM: "基于文档的准确答案 + 引用"
✅ Claude: 基于真实 API 编写代码

结果：一次写对，没有幻觉！
```

**核心工作流**:
1. 一次性设置：`python scripts/run.py auth_manager.py setup`
2. 创建知识库：上传文档到 NotebookLM 并分享链接
3. 添加到库：`python scripts/run.py notebook_manager.py add --url "URL"`
4. 开始查询：`python scripts/run.py ask_question.py --question "..."`

**为什么不用本地 RAG**:
- Token 消耗：最少（不反复读取文件）
- 幻觉率：最低（源导向回答）
- 设置时间：5分钟（无需 embeddings、向量数据库）
- 答案质量：专家级（Gemini 2.5 合成）

**限制**:
- 仅限本地 Claude Code（Web UI 不支持）
- 免费版每日查询限制（50次/天）
- 需要手动上传文档到 NotebookLM

</details>

[⬆️ 回到顶部 / Back to Top](#-claude-skills-快速参考--quick-reference)

---

## 🔧 工具技能（5个） / Tools (5)

<details>
<summary><strong>📖 点击展开/折叠 / Click to Expand/Collapse</strong></summary>

### 🛠️ Skill Creator / 技能创建器

**是什么 / What**:
创建新Claude技能

**能做什么 / Capabilities**:
- 技能文件结构
- YAML前置元数据
- 文档格式
- 测试验证

**什么时候用 / When to Use**:
- 创建新技能时
- 自定义工作流时
- 分享技能时
- 扩展功能时

**怎么用 / How to Use**:
```
告诉 Claude："帮我创建一个新技能"
Claude 会使用 skill-creator 技能
创建符合标准的技能文件
```

---

### 🔌 MCP Builder / MCP构建器

**是什么 / What**:
构建Model Context Protocol服务器

**能做什么 / Capabilities**:
- 连接外部工具
- 资源和工具定义
- 服务器实现
- API集成

**什么时候用 / When to Use**:
- 构建MCP服务器时
- 连接API时
- 自定义工具时
- 扩展Claude能力时

**怎么用 / How to Use**:
```
告诉 Claude："帮我构建一个MCP服务器"
Claude 会使用 mcp-builder 技能
创建MCP服务器代码
```

---

### 🤝 Doc Coauthoring / 文档协作

**是什么 / What**:
协作文档编辑

**能做什么 / Capabilities**:
- 跟踪更改
- 多贡献者
- 版本控制
- 审查批准

**什么时候用 / When to Use**:
- 协作文档时
- 收集反馈时
- 解决冲突时
- 团队写作时

**怎么用 / How to Use**:
```
告诉 Claude："帮我协作编辑这个文档"
Claude 会使用 doc-coauthoring 技能
管理协作编辑流程
```

---

### 📢 Internal Comms / 内部沟通

**是什么 / What**:
创建专业内部沟通

**能做什么 / Capabilities**:
- 公告模板
- 项目更新
- 会议记录
- 行动项跟踪

**什么时候用 / When to Use**:
- 公司公告时
- 项目更新时
- 会议记录时
- 团队沟通时

**怎么用 / How to Use**:
```
告诉 Claude："帮我写个项目更新"
Claude 会使用 internal-comms 技能
生成专业的沟通模板
```

---

### 🎨 Brand Guidelines / 品牌指南

**是什么 / What**:
应用Anthropic品牌标准

**能做什么 / Capabilities**:
- 品牌颜色
- 字体规范
- 标志使用
- 语气语调

**什么时候用 / When to Use**:
- 创建品牌内容时
- 应用主题时
- 保持一致性时
- 品牌建设时

**怎么用 / How to Use**:
```
告诉 Claude："应用Anthropic品牌标准"
Claude 会使用 brand-guidelines 技能
确保符合品牌规范
```

</details>

[⬆️ 回到顶部 / Back to Top](#-claude-skills-快速参考--quick-reference)

---

## 📊 使用场景总览 / Usage Scenarios Overview

<details>
<summary><strong>📖 点击展开工作流程 / Click to Expand Workflows</strong></summary>

### 🚀 完整开发流程 / Complete Development Flow
```
1. 💡 有想法 → brainstorming
2. 📋 做计划 → writing-plans (简单) / planning-with-files (复杂)
3. 🚀 去实施 → subagent-driven-development + test-driven-development
4. 👁️ 审查 → requesting-code-review + receiving-code-review
5. ✅ 验证 → verification-before-completion
6. 🎬 完成 → finishing-a-development-branch
```

### 📄 文档自动化流程 / Document Automation Flow
```
PDF提取数据 → Excel分析 → Word生成报告 → PowerPoint演示
```

### 🔍 智能研究流程 / Intelligent Research Flow
```
上传文档到 NotebookLM → notebooklm-skill 查询 → planning-with-files 积累知识 → 生成研究报告
```

### 🌐 Web开发流程 / Web Development Flow
```
设计UI → frontend-design → 构件实现 → web-artifacts-builder → 测试 → webapp-testing
```

### 🎨 视觉创作流程 / Visual Creation Flow
```
算法艺术 → algorithmic-art → Canvas动画 → canvas-design → GIF动画 → slack-gif-creator → 主题应用 → theme-factory
```

</details>

---

## 💡 快速查找指南 / Quick Find Guide

<details>
<summary><strong>📖 点击展开查找指南 / Click to Expand Guide</strong></summary>

### 我想... / I want to...

**开发功能 / Develop Features**
→ brainstorming → writing-plans → test-driven-development

**修bug / Fix Bugs**
→ systematic-debugging → test-driven-development → verification-before-completion

**处理文档 / Handle Documents**
→ PDF分析 → pdf
→ Word文档 → docx
→ PowerPoint → pptx
→ Excel表格 → xlsx

**创建Web / Create Web**
→ 设计界面 → frontend-design
→ 构建构件 → web-artifacts-builder
→ 测试应用 → webapp-testing

**创建视觉内容 / Create Visuals**
→ 生成艺术 → algorithmic-art
→ Canvas艺术 → canvas-design
→ Slack GIF → slack-gif-creator
→ 应用主题 → theme-factory

**研究与高级工作流 / Research & Advanced**
→ 复杂任务规划 → planning-with-files
→ 智能文档查询 → notebooklm-skill

**工具扩展 / Extend Tools**
→ 创建技能 → skill-creator
→ 构建MCP → mcp-builder
→ 协作文档 → doc-coauthoring
→ 内部沟通 → internal-comms
→ 品牌应用 → brand-guidelines

</details>

---

## 🎯 技能组合建议 / Skill Combinations

<details>
<summary><strong>📖 点击展开最佳组合 / Click to Expand Combinations</strong></summary>

### 最佳组合 / Best Combinations

**1. 质量优先开发 / Quality-First Development**
```
brainstorming + writing-plans + subagent-driven-development +
test-driven-development + requesting-code-review +
verification-before-completion
```

**2. 快速原型 / Rapid Prototyping**
```
brainstorming + frontend-design + web-artifacts-builder
```

**3. 文档自动化 / Document Automation**
```
pdf + xlsx + docx + pptx
```

**4. 完整Web项目 / Complete Web Project**
```
frontend-design + web-artifacts-builder + webapp-testing +
slack-gif-creator + theme-factory
```

**5. 团队协作 / Team Collaboration**
```
writing-plans + doc-coauthoring + internal-comms +
requesting-code-review + receiving-code-review
```

**6. 复杂研究项目 / Complex Research Project**
```
planning-with-files + notebooklm-skill + systematic-debugging +
docx/pptx (生成研究报告)
```

**7. 文档驱动开发 / Document-Driven Development**
```
notebooklm-skill (查询技术文档) + planning-with-files (记录发现) +
test-driven-development (基于真实 API 实现)
```

</details>

---

## 🔖 书签 / Bookmarks

<details>
<summary><strong>📖 点击展开书签 / Click to Expand Bookmarks</strong></summary>

### 按用途查找 / Find by Purpose
- 🚀 [开始新项目](#-软件开发技能14个-software-development-14)
- 📄 [处理文档](#-文档处理技能4个-document-processing-4)
- 🌐 [开发Web应用](#-web开发技能3个-web-development-3)
- 🎨 [创建视觉内容](#-视觉媒体技能4个-visual--media-4)
- 📚 [研究与高级工作流](#-研究与高级工作流技能2个-research--advanced-workflows-2)
- 🔧 [扩展工具](#-工具技能5个-tools-5)

### 按场景查找 / Find by Scenario
- 💡 [有个想法](#-brainstorming-头脑风暴)
- 🐛 [遇到bug](#-systematic-debugging-系统化调试)
- 📊 [分析数据](#-xlsx-excel电子表格处理)
- 🎨 [设计界面](#-frontend-design前端uiux设计)
- 🧪 [测试应用](#-webapp-testing-web应用测试)

</details>

---

_💡 提示：点击每个类别的标题可以展开/折叠内容。技能会自动识别上下文并调用！也可以手动使用 `/skill-name` 命令_

_💡 Tip: Click on category headers to expand/collapse content. Skills auto-detect context! You can also use `/skill-name` command manually_
