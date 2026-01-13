# 🚀 Claude Skills 快速参考 / Quick Reference

## 🎯 所有技能通俗解释 / All Skills Explained Simply

---

## 📂 软件开发技能（14个） / Software Development (14)

### 🧠 Brainstorming / 头脑风暴
**是什么**: 像和产品经理聊天，把模糊想法变清晰方案
**能做什么**: 问问题、看代码、探索方案、设计实施
**什么时候用**: 加功能、改代码、从头设计、不确定怎么做
**举例**: "想加登录" → 技能问：什么方式？存什么数据？有现成的吗？→ 给你完整方案

### 📝 Writing Plans / 编写计划
**是什么**: 像项目经理拆任务，把大功能变清单
**能做什么**: 拆任务、定标准、找依赖、可并行
**什么时候用**: 头脑风暴后、写代码前、复杂项目、多人协作
**举例**: "用户认证" → 拆成：OAuth控制器、JWT中间件、用户模型、集成测试

### 🤖 Subagent-Driven Development / 子代理驱动开发
**是什么**: 像有开发团队，每任务派新助手+双重检查
**能做什么**: 新助手做任务、两次审查（计划+质量）、快速迭代
**什么时候用**: 执行计划、快速开发、复杂项目、保证质量
**举例**: 任务1派新助手 → 做完 → 审查1：符合计划？审查2：代码质量？→ 修复 → 继续

### 🧪 Test-Driven Development / 测试驱动开发
**是什么**: 先写测试（失败）→ 写代码（通过）→ 优化代码，三步循环
**能做什么**: 确保代码工作、防止改坏、易维护、提供示例
**什么时候用**: 写功能、修bug、重构代码、任何时候写代码
**举例**: 测试add_user() → 失败 → 写User.save() → 通过 → 加参数验证 → 还是通过

### ⚡ Executing Plans / 执行计划
**是什么**: 批量处理任务，每3个任务停下来检查
**能做什么**: 批量执行、定期检查、及时调整、跟踪进度
**什么时候用**: 有书面计划、任务多、需定期检查、长时间开发
**举例**: 9任务 → 批1(1-3)检查 → 批2(4-6)检查发现问题 → 修复 → 批3(7-9)完成

### ✅ Verification Before Completion / 完成前验证
**是什么**: 关bug前，先验证真的修好了吗
**能做什么**: 测试修复、验证根本原因、检查副作用、防止过早关闭
**什么时候用**: 修完bug、完成任务、关闭issue、说"搞定了"
**举例**: 登录特殊字符失败 → 加编码 → 测试成功 → 检查普通密码 → 也成功 → 关闭bug

### 🎬 Finishing Development Branch / 完成开发分支
**是什么**: 功能做完了，三种方式处理（直接合并、创建PR、丢弃）
**能做什么**: 直接合并小改动、创建PR大改动、丢弃失败实验
**什么时候用**: 功能完成、准备合并、实验不需要、分支太乱
**举例**: 小改动直接合并；大改动创建PR等审查；实验失败直接删分支

### 👁️ Requesting Code Review / 请求代码审查
**是什么**: 写完代码请别人（或AI）检查问题
**能做什么**: 系统化审查、两阶段检查、早发现问题、获取建议
**什么时候用**: 完成任务、完成功能、合并代码、被卡住
**举例**: 做完任务2 → 请求审查 → 发现：缺进度指示器 → 修复 → 继续

### 📥 Receiving Code Review / 接收代码审查
**是什么**: 别人审查你的代码，建设性回应
**能做什么**: 技术评价、错时反驳、对时学习、保持专业
**什么时候用**: 收到反馈、需回应建议、不确定对错、讨论方案
**举例**: 建议"用async/await" → 分析：确实更好 → 接受并学习；建议"删日志" → 分析：生产需要 → 礼貌反驳

### 🚀 Dispatching Parallel Agents / 调度并行子代理
**是什么**: 同时派几个AI助手解决问题，比较结果选最好
**能做什么**: 并发解决、不同视角、探索方案、更快迭代
**什么时候用**: 多独立问题、探索方案、不确定方法、需要新思路
**举例**: 优化慢查询 → 助手1：加索引（10倍）；助手2：优化JOIN（5倍）；助手3：Redis缓存（100倍但复杂）→ 选助手1

### 🌳 Using Git Worktrees / 使用Git Worktrees
**是什么**: 同仓库多个工作目录，同时在不同分支工作
**能做什么**: 同时多功能、热修复不打断、轻松切换、避免stash/pop
**什么时候用**: 同时做多事、紧急修复、测试方案、审查代码
**举例**: 主目录/ + 认证分支/ + UI分支/ + 修复分支/ → 修复时不需要stash开发分支

### 🔍 Systematic Debugging / 系统化调试
**是什么**: 有条理排查bug，不瞎改代码碰运气
**能做什么**: 系统调查、找根本原因、验证假设、记录发现
**什么时候用**: 发现bug、不知道怎么修、复杂bug、需理解问题
**举例**: 登录间歇失败 → 理解：10%失败 → 假设：竞态？编码？超时？→ 测试：编码问题证实 → 修复 → 100次成功

### 📘 Using Superpowers / Superpowers使用指南
**是什么**: 教你怎么用这些技能的说明书
**能做什么**: 技能规则、危险警示、最佳实践、完整流程
**什么时候用**: 第一次用、不清楚用哪个、学最佳实践、遇问题
**举例**: 完整流程：想法→头脑风暴→计划→实施→审查→验证→完成；危险信号：跳过审查、不头脑风暴、TDD写错

### ✍️ Writing Skills / 编写技能
**是什么**: 用TDD方法写技能文档，先测试再写文档
**能做什么**: 先用再写、真实验证、迭代文档、确保准确
**什么时候用**: 创建技能、改进技能、文档过时、分享技能
**举例**: RED用技能发现缺错误处理 → GREEN写文档覆盖差距 → REFACTOR优化加示例

---

## 📄 文档处理技能（4个） / Document Processing (4)

### 📕 PDF / PDF文档处理
**是什么**: 从PDF提取内容（文本、表格、图像）
**能做什么**: 提取文本、解析表格、提取图像、OCR扫描
**什么时候用**: 分析PDF、解析发票、分析论文、PDF转文本
**举例**: 财务报告PDF → 提取所有表格 → 分析到Excel

### 📗 DOCX / Word文档处理
**是什么**: 创建和编辑Word文档
**能做什么**: 创建文档、读写文件、修改格式、加表格图像
**什么时候用**: 生成报告、创建发票、填充模板、邮件合并
**举例**: 自动生成月度报告 → 加标题、表格、图表 → 保存report.docx

### 📘 PPTX / PowerPoint创建编辑
**是什么**: 创建PowerPoint演示文稿
**能做什么**: 创建幻灯片、加内容、加形状图像、应用主题
**什么时候用**: 自动报告、培训材料、数据可视化、模板生成
**举例**: 销售数据 → 创建PPT → 标题页、数据页、图表页 → 保存presentation.pptx

### 📙 XLSX / Excel电子表格处理
**是什么**: 操作Excel（公式、图表、数据）
**能做什么**: 读写Excel、加公式、创建图表、应用格式
**什么时候用**: 财务报告、数据分析、发票生成、数据导入导出
**举例**: 销售数据 → 创建Excel → 加公式计算总价 → 创建柱状图 → 保存sales.xlsx

---

## 🌐 Web开发技能（3个） / Web Development (3)

### 💻 Frontend Design / 前端UI/UX设计
**是什么**: 用React和Tailwind设计现代界面
**能做什么**: 组件设计、响应式布局、现代样式
**什么时候用**: 设计UI/UX、创建组件、重构界面
**举例**: 登录表单 → React组件 + Tailwind样式 → 渐变背景、输入框、按钮

### 🎨 Web Artifacts Builder / Web构件构建器
**是什么**: 用React+Tailwind创建精美HTML构件
**能做什么**: React组件、Tailwind样式、生产构建
**什么时候用**: 创建HTML构件、快速开发、优化构建
**举例**: npm创建项目 → React组件 → Tailwind样式 → npm run build → 生产就绪

### 🧪 WebApp Testing / Web应用测试
**是什么**: 用Playwright测试Web应用
**能做什么**: 自动测试、跨浏览器、视觉回归
**什么时候用**: 测试应用、验证功能、回归测试
**举例**: 测试登录页 → 打开localhost:3000 → 检查标题 → 填表单 → 点按钮 → 验证成功

---

## 🎨 视觉媒体技能（4个） / Visual & Media (4)

### 🎨 Algorithmic Art / 算法艺术
**是什么**: 用算法和数学模式创建艺术
**能做什么**: 程序化生成、数学模式、受控随机
**什么时候用**: 创建生成艺术、实验视觉效果、设计图案
**举例**: 随机画50个圆 → 随机位置、大小、颜色 → 保存generative_art.png

### 🖼️ Canvas Design / Canvas视觉艺术
**是什么**: 用HTML5 Canvas创建视觉艺术
**能做什么**: 交互图形、动画、复杂可视化
**什么时候用**: 创建Canvas艺术、动画效果、数据可视化
**举例**: Canvas → 渐变动画 → 移动圆圈 → requestAnimationFrame循环

### 🎞️ Slack GIF Creator / Slack GIF创建器
**是什么**: 创建为Slack优化的动画GIF
**能做什么**: 适当尺寸、优化文件大小、流畅动画
**什么时候用**: 创建Slack emoji、Slack消息GIF、团队动画
**举例**: 12帧动画 → 128x128像素 → 10fps → 保存slack_emoji.gif

### 🎭 Theme Factory / 主题工厂
**是什么**: 应用10个专业主题到内容
**能做什么**: 颜色调板、字体、样式模式
**什么时候用**: 应用主题、设计一致性、专业外观
**举例**: Midnight Galaxy主题 → 深蓝紫色、现代字体、科技感 → 应用到文档

---

## 🔧 工具技能（5个） / Tools (5)

### 🛠️ Skill Creator / 技能创建器
**是什么**: 创建新Claude技能
**能做什么**: 技能结构、YAML前置元数据、文档格式、测试验证
**什么时候用**: 创建新技能、自定义工作流、分享技能
**举例**: 新技能data-analysis → YAML元数据 → 概述、快速开始、特性、最佳实践 → 部署

### 🔌 MCP Builder / MCP构建器
**是什么**: 构建Model Context Protocol服务器
**能做什么**: 连接外部工具到Claude、资源工具定义、服务器实现
**什么时候用**: 构建MCP服务器、连接API、自定义工具
**举例**: MCP服务器 → database工具 → query_database函数 → db://tables资源 → Claude可调用

### 🤝 Doc Coauthoring / 文档协作
**是什么**: 协作文档编辑
**能做什么**: 跟踪更改、多贡献者、版本控制、审查批准
**什么时候用**: 协作文档、收集反馈、解决冲突
**举例**: 项目提案 → @alice审查时间线 → @bob澄清阶段3 → 收集反馈 → 解决冲突 → 定稿

### 📢 Internal Comms / 内部沟通
**是什么**: 创建专业内部沟通
**能做什么**: 公告、更新、报告、会议记录
**什么时候用**: 公司公告、项目更新、会议记录、行动项
**举例**: 项目更新模版 → 项目名、状态、已完成、进行中、阻碍者 → 发给团队

### 🎨 Brand Guidelines / 品牌指南
**是什么**: 应用Anthropic品牌标准
**能做什么**: 颜色、字体、标志使用、语气语调
**什么时候用**: 创建品牌内容、应用主题、保持一致性
**举例**: Anthropic品牌 → 蓝色#4A6FA5、Inter字体、专业但平易近人 → 应用到组件

---

## 📊 使用场景总览 / Usage Scenarios Overview

### 🚀 完整开发流程 / Complete Development Flow
```
1. 💡 有想法 → brainstorming
2. 📋 做计划 → writing-plans
3. 🚀 去实施 → subagent-driven-development + test-driven-development
4. 👁️ 审查 → requesting-code-review + receiving-code-review
5. ✅ 验证 → verification-before-completion
6. 🎬 完成 → finishing-a-development-branch
```

### 📄 文档自动化流程 / Document Automation Flow
```
PDF提取数据 → Excel分析 → Word生成报告 → PowerPoint演示
```

### 🌐 Web开发流程 / Web Development Flow
```
设计UI → frontend-design → 构件实现 → web-artifacts-builder → 测试 → webapp-testing
```

### 🎨 视觉创作流程 / Visual Creation Flow
```
算法艺术 → algorithmic-art → Canvas动画 → canvas-design → GIF动画 → slack-gif-creator → 主题应用 → theme-factory
```

---

## 💡 快速查找指南 / Quick Find Guide

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

**工具扩展 / Extend Tools**
→ 创建技能 → skill-creator
→ 构建MCP → mcp-builder
→ 协作文档 → doc-coauthoring
→ 内部沟通 → internal-comms
→ 品牌应用 → brand-guidelines

---

## 🎯 技能组合建议 / Skill Combinations

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

---

_💡 提示：技能会自动识别上下文并调用！也可以手动使用 `/skill-name` 命令_
