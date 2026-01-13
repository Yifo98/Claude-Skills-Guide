# 🚀 Claude Skills 快速参考 / Quick Reference

## 🎯 所有技能通俗解释 / All Skills Explained Simply

---

## 📂 软件开发技能（14个） / Software Development (14)

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

**举例 / Example**:
```
计划：做用户认证功能

流程：
任务1：实现OAuth登录
  📤 派个新助手来做
  ✅ 做完了
  👁️ 第一次审查：符合计划吗？✓
  👁️ 第二次审查：代码质量好吗？有个小问题
  🔧 修复问题
  ➡️ 继续下一个任务

每个任务都严格检查，不会留下隐患！
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

**举例 / Example**:
```
要写一个"加用户"功能

🔴 RED - 先写测试（会失败）
def test_add_user():
    result = add_user("Alice")
    assert result.id is not None
运行：❌ 失败（函数还不存在）

🟢 GREEN - 写最小代码让测试通过
def add_user(name):
    user = User(name=name).save()
    return user
运行：✅ 通过

🔵 REFACTOR - 优化代码
def add_user(name: str) -> User:
    """添加新用户到数据库"""
    if not name:
        raise ValueError("名字不能为空")
    return User(name=name).save()
运行：✅ 还是通过，但代码更好了
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

**举例 / Example**:
```
计划：9个任务

📦 第1批（任务1-3）：
  ✅ 任务1
  ✅ 任务2
  ✅ 任务3
  ⏸️ 检查点：代码审查
  👉 发现小问题，但不影响继续

📦 第2批（任务4-6）：
  ✅ 任务4
  ✅ 任务5
  ✅ 任务6
  ⏸️ 检查点：代码审查
  👉 发现重要问题，修复后再继续

📦 第3批（任务7-9）：
  ✅ 任务7
  ✅ 任务8
  ✅ 任务9
  ⏸️ 最终检查：全部完成！

不会等到最后才发现前面做错了！
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

**举例 / Example**:
```
Bug："登录时特殊字符会失败"

修复：添加了密码编码

验证流程：
1️⃣ 重现bug：用"p@ss!123"登录 → 失败 ✓
2️⃣ 应用修复：添加base64编码
3️⃣ 测试修复：用"p@ss!123"登录 → 成功 ✓
4️⃣ 检查副作用：普通密码还能用吗？→ 能 ✓
5️⃣ 关闭bug：✓ 已验证

而不是："我觉得应该修好了" → 关闭 ❌
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

**举例 / Example**:
```
分支：feature/user-auth
状态：所有任务完成，测试通过

选项选择：
1️⃣ 直接合并（小改动，风险低）
   → git merge feature/user-auth
   → 删除分支

2️⃣ 创建PR（大改动，需要审查）
   → 创建Pull Request
   → 写清楚改了什么
   → 等同事审查
   → 审查通过后合并

3️⃣ 丢弃分支（实验失败，有更好的方案）
   → 直接删除分支
   → 不合并

选择合适的结束方式，保持代码库整洁！
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

**举例 / Example**:
```
刚做完：任务2 - 添加验证函数

请求代码审查：
📋 做了什么：验证和修复函数
📋 计划是什么：部署计划的任务2
📋 代码范围：a7981ec 到 3df7661

审查结果：
✅ 优点：架构清晰，有真实测试
⚠️ 问题：
  重要：缺少进度指示器
  次要：魔法数字 100
📊 评估：可以继续

行动：修复进度指示器，然后继续
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

**怎么用 / How to Use**:
```
收到审查反馈后，告诉 Claude："帮我分析这些建议"
Claude 会使用 receiving-code-review
帮你技术性地评估每条建议
```

**举例 / Example**:
```
审查者建议："用 async/await 代替 Promise"

你的分析：
- 当前代码用 .then() 链
- 工作正常，测试通过
- async/await 确实更易读

决定：✅ 接受建议
行动：重构为 async/await
学习：新代码优先用 async/await

---

审查者建议："删除 console.log"

你的分析：
- 这些是有意的调试日志
- 帮助排查生产问题
- 文档中有说明

决定：❌ 礼貌反驳
理由：
- 这是生产调试工具
- 不是偶然的调试语句
- 已在文档中说明
```

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

**怎么用 / How to Use**:
```
告诉 Claude："用几个不同的方案解决这个问题"
Claude 会使用 dispatching-parallel-agents
同时运行多个子代理探索不同方案
```

**举例 / Example**:
```
问题："优化慢的数据库查询"

🤖 助手1（分析执行计划）：
  → 建议：添加索引
  → 预计提升：10倍

🤖 助手2（重构查询结构）：
  → 建议：优化JOIN逻辑
  → 预计提升：5倍

🤖 助手3（研究缓存方案）：
  → 建议：使用Redis缓存
  → 预计提升：100倍
  → 复杂度：高

比较结果：助手1方案简单效果好，选它！
```

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

**怎么用 / How to Use**:
```
告诉 Claude："我想同时在多个分支上工作"
Claude 会使用 using-git-worktrees
帮你设置多个工作目录
```

**举例 / Example**:
```
目录结构：
my-project/         ← 主分支（main）
my-project-auth/    ← 认证功能分支
my-project-ui/      ← UI功能分支
my-project-fix/     ← 紧急修复分支

使用场景：
1. 在 my-project-auth/ 开发登录功能
2. 突然需要紧急修复
3. 切换到 my-project-fix/ 修复
4. 修复完了，切回 my-project-auth/ 继续开发
   （不需要 stash/pop，状态都保留着！）
```

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

**举例 / Example**:
```
Bug："用户登录间歇性失败"

1️⃣ 理解问题：
   - 重现：10%的概率失败
   - 特定密码模式才会触发
   - 没有错误信息

2️⃣ 形成假设：
   - 假设1：竞态条件
   - 假设2：密码编码问题
   - 假设3：数据库连接超时

3️⃣ 测试假设：
   - 测试假设1：加延迟 → 没效果
   - 测试假设2：记录编码 → 发现特殊字符失败
   - 假设2被证实！

4️⃣ 修复验证：
   - 添加特殊字符转义
   - 验证：100次登录全部成功
   - 关闭bug ✓

而不是："试试改这个...再试试改那个..."
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

**怎么用 / How to Use**:
```
随时可以问 Claude："这些技能怎么配合使用？"
Claude 会使用 using-superpowers
解释技能之间的协作关系
```

**举例 / Example**:
```
完整工作流：
💡 想法 → brainstorming
📋 计划 → writing-plans
🚀 实施 → subagent-driven-development → test-driven-development
👁️ 审查 → requesting-code-review
✅ 验证 → verification-before-completion
🎬 完成 → finishing-a-development-branch

危险信号：
❌ 跳过代码审查技能
❌ 复杂任务不头脑风暴
❌ 错误使用TDD（先写代码）

技能会自动识别上下文并调用！
```

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

**怎么用 / How to Use**:
```
创建新技能时，告诉 Claude："帮我创建一个技能"
Claude 会使用 writing-skills
用TDD方法编写技能文档
```

**举例 / Example**:
```
🔴 RED - 使用技能
  在真实场景中使用新技能
  → 发现：文档中少了错误处理说明

🟢 GREEN - 编写文档
  添加错误处理章节
  → 覆盖识别的差距

🔵 REFACTOR - 优化文档
  提高清晰度
  添加示例
  完善结构
  → 文档更好了

而不是：先写一堆理论文档，结果发现跟实际使用不一样
```

---

## 📄 文档处理技能（4个） / Document Processing (4)

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

**举例 / Example**:
```
文件：财务报告.pdf

操作：
1️⃣ 提取所有表格
2️⃣ 提取文本内容
3️⃣ 识别关键数据
4️⃣ 导出到Excel分析

结果：所有财务数据结构化提取，方便分析
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

**举例 / Example**:
```
任务：自动生成月度报告

操作：
1️⃣ 创建文档
2️⃣ 添加标题和段落
3️⃣ 插入数据表格
4️⃣ 添加图表
5️⃣ 应用格式
6️⃣ 保存 report.docx

结果：专业的Word报告自动生成
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

**举例 / Example**:
```
任务：销售数据演示

操作：
1️⃣ 标题幻灯片
2️⃣ 数据概览页
3️⃣ 图表展示页
4️⃣ 结论页
5️⃣ 应用主题
6️⃣ 保存 presentation.pptx

结果：专业的演示文稿自动生成
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

**举例 / Example**:
```
任务：销售数据报表

操作：
1️⃣ 创建工作簿
2️⃣ 添加数据行
3️⃣ 添加公式（总计、平均）
4️⃣ 创建柱状图
5️⃣ 应用格式
6️⃣ 保存 sales.xlsx

结果：专业的Excel报表自动生成
```

---

## 🌐 Web开发技能（3个） / Web Development (3)

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

**举例 / Example**:
```
任务：设计登录表单

结果：
- React 组件结构
- Tailwind CSS 样式
- 渐变背景
- 表单验证
- 响应式设计
- 完整可运行的代码
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

**举例 / Example**:
```
任务：创建数据仪表板

步骤：
1️⃣ npm create vite 创建项目
2️⃣ 安装 Tailwind CSS
3️⃣ 创建仪表板组件
4️⃣ 添加图表和表格
5️⃣ npm run build 构建
6️⃣ 部署到生产

结果：生产就绪的HTML构件
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

**举例 / Example**:
```
任务：测试登录功能

测试代码：
1️⃣ 打开登录页面
2️⃣ 填写用户名和密码
3️⃣ 点击登录按钮
4️⃣ 验证跳转到首页
5️⃣ 截图保存

运行测试：
npx playwright test
结果：所有测试通过 ✓
```

---

## 🎨 视觉媒体技能（4个） / Visual & Media (4)

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

**举例 / Example**:
```
任务：生成几何艺术

操作：
1️⃣ 使用Perlin噪声
2️⃣ 生成随机几何图形
3️⃣ 应用颜色渐变
4️⃣ 保存为PNG

结果：独特的生成艺术作品
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

**举例 / Example**:
```
任务：创建动态波浪效果

操作：
1️⃣ 创建Canvas元素
2️⃣ 使用requestAnimationFrame
3️⃣ 绘制动态波浪
4️⃣ 添加颜色渐变
5️⃣ 响应鼠标交互

结果：流畅的动画效果
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

**举例 / Example**:
```
任务：创建庆祝动画

操作：
1️⃣ 设计12帧动画
2️⃣ 尺寸：128x128像素
3️⃣ 帧率：15fps
4️⃣ 优化颜色
5️⃣ 保存celebrate.gif

结果：Slack团队专用的庆祝emoji
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

**举例 / Example**:
```
任务：为文档应用主题

操作：
1️⃣ 选择：午夜银河
2️⃣ 应用颜色：深蓝#1E3A8A、紫色#8B5CF6
3️⃣ 应用字体：Inter，现代科技感
4️⃣ 调整样式
5️⃣ 预览效果

结果：专业的深色主题文档
```

---

## 🔧 工具技能（5个） / Tools (5)

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

**举例 / Example**:
```
任务：创建数据分析技能

步骤：
1️⃣ 创建技能目录
2️⃣ 编写YAML元数据
3️⃣ 添加文档说明
4️⃣ 编写使用示例
5️⃣ 部署到skills目录

结果：新技能立即可用
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

**举例 / Example**:
```
任务：数据库MCP服务器

步骤：
1️⃣ 创建MCP服务器
2️⃣ 定义query_database工具
3️⃣ 定义db://tables资源
4️⃣ 实现错误处理
5️⃣ 启动服务器

结果：Claude可以直接查询数据库
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

**举例 / Example**:
```
任务：团队编写项目提案

协作流程：
1️⃣ 创建文档
2️⃣ @alice 审查时间线
3️⃣ @bob 澄清阶段3
4️⃣ 收集所有反馈
5️⃣ 整合意见
6️⃣ 最终定稿

结果：团队共识的完整提案
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

**举例 / Example**:
```
任务：项目进度更新

模板：
📊 项目：用户认证系统
状态：按计划进行
已完成：
✅ OAuth集成
✅ 用户模型
进行中：
🔄 JWT中间件
阻碍：
🚂 无

结果：清晰专业的进度报告
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

**举例 / Example**:
```
任务：创建品牌组件

标准：
颜色：
- 主色：#4A6FA5（蓝色）
- 文字：#1E293B（深灰）
- 背景：#F8FAFC（浅灰）

字体：
- 标题：Inter，700
- 正文：Inter，400

语气：
- 专业但平易近人
- 清晰简洁

结果：符合品牌规范的组件
```

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

## 🔖 书签 / Bookmarks

### 按用途查找 / Find by Purpose
- 🚀 [开始新项目](#-软件开发技能14个-software-development-14)
- 📄 [处理文档](#-文档处理技能4个-document-processing-4)
- 🌐 [开发Web应用](#-web开发技能3个-web-development-3)
- 🎨 [创建视觉内容](#-视觉媒体技能4个-visual--media-4)
- 🔧 [扩展工具](#-工具技能5个-tools-5)

### 按场景查找 / Find by Scenario
- 💡 [有个想法](#-brainstorming-头脑风暴)
- 🐛 [遇到bug](#-systematic-debugging-系统化调试)
- 📊 [分析数据](#-xlsx-excel电子表格处理)
- 🎨 [设计界面](#-frontend-design前端uiux设计)
- 🧪 [测试应用](#-webapp-testing-web应用测试)

---

_💡 提示：技能会自动识别上下文并调用！也可以手动使用 `/skill-name` 命令_
