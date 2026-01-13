# 🎯 Software Development Skills Guide / 软件开发技能指南

## 🎯 软件开发技能指南

> __Official Sources / 官方来源:__
> Based on obra/superpowers repository by @obra
> 基于 obra/superpowers 仓库
>
> Please visit the official repository for the most up-to-date information.
> 请访问官方仓库获取最新信息。

---

## 📋 Overview / 概述

Software development skills provide a complete workflow from idea to production. These skills implement modern development practices including test-driven development, systematic debugging, code reviews, and automated verification.

软件开发技能提供从创意到生产的完整工作流。这些技能实现了现代开发实践，包括测试驱动开发、系统化调试、代码审查和自动验证。

### Complete Workflow / 完整工作流

```
Idea → Plan → Code → Test → Review → Verify → Merge
  ↓      ↓      ↓      ↓       ↓       ↓       ↓
brainstorm  writing  TDD  code  verify  finish
            plans    review
```

本指南涵盖了：
- **Creative Phase / 创意阶段** - brainstorming, writing-plans
- **Implementation Phase / 实现阶段** - test-driven-development, subagent-driven-development, executing-plans
- **Quality Assurance / 质量保证** - systematic-debugging, requesting-code-review, receiving-code-review, verification-before-completion
- **Workflow Management / 工作流管理** - dispatching-parallel-agents, using-git-worktrees, finishing-a-development-branch
- **Meta Skills / 元技能** - using-superpowers, writing-skills

---

## 🧠 Brainstorming / 头脑风暴

> __Quick Access / 快速访问:__ Use before any creative work / 在任何创造性工作前使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像和产品经理聊天一样，把你的模糊想法变成清晰的设计方案
**Like chatting with a product manager to turn vague ideas into clear designs**

**能做什么 / Capabilities**:
- 问你问题搞清楚需求 / Ask questions to understand requirements
- 看看现有代码怎么做 / Check existing code patterns
- 探索几种技术方案 / Explore multiple technical approaches
- 设计出实施方案 / Design implementation approach

**什么时候用 / When to Use**:
- 要加新功能时 / Adding new features
- 要改现有功能时 / Modifying existing features
- 要从头设计时 / Starting from scratch
- 不确定怎么做时 / Unsure how to proceed

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

### Purpose / 作用

Turn vague ideas into fully-formed designs with:
将模糊的想法转化为完整的设计：

- Understanding current project state
- 理解当前项目状态
- Asking clarifying questions
- 提出澄清性问题
- Exploring technical approaches
- 探索技术方法
- Creating structured designs
- 创建结构化设计

### Key Features / 主要特性

✨ **Context-Aware / 上下文感知**
  - Reads existing codebase first
  - 首先读取现有代码库
  - Asks questions one at a time
  - 一次问一个问题
  - Avoids premature solutions
  - 避免过早的解决方案

✨ **Systematic Approach / 系统化方法**
  - Explore constraints first
  - 首先探索约束
  - Then design approach
  - 然后设计方法
  - Finally validate
  - 最后验证

### Example / 示例

```
User: "Add user authentication"

You (brainstorming skill):
1. Read current project structure
2. Ask: "Which authentication method?"
   - OAuth (Google/GitHub)
   - JWT tokens
   - Session-based
3. Ask: "What data needs storing?"
4. Ask: "Any existing auth system?"
5. Design authentication flow
6. Present implementation plan
```

### Best Practices / 最佳实践

✅ **Always / 始终**
  - Start by reading existing code
  - 从阅读现有代码开始
  - Ask questions one at a time
  - 一次问一个问题
  - Explore multiple approaches
  - 探索多种方法

❌ **Never / 不要**
  - Jump to implementation immediately
  - 立即跳到实现
  - Ask all questions at once
  - 一次问所有问题
  - Ignore existing patterns
  - 忽略现有模式

---

## 📝 Writing Plans / 编写计划

> __Quick Access / 快速访问:__ Use after brainstorming, before coding / 头脑风暴后使用，编码前使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像项目经理写任务清单，把大任务拆成一个个小步骤
**Like a project manager breaking big tasks into small steps**

**能做什么 / Capabilities**:
- 把大功能拆成小任务 / Break features into small tasks
- 定义每个任务的完成标准 / Define success criteria for each task
- 找出任务之间的依赖关系 / Identify dependencies
- 让任务可以并行执行 / Enable parallel execution

**什么时候用 / When to Use**:
- 头脑风暴结束后 / After brainstorming
- 要开始写代码前 / Before writing code
- 项目比较复杂时 / For complex projects
- 需要多人协作时 / For team collaboration

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

### Purpose / 作用

Create detailed implementation plans that:
创建详细的实施计划：

- Break down work into tasks
  - 将工作分解为任务
- Define success criteria
  - 定义成功标准
- Identify dependencies
  - 识别依赖关系
- Enable parallel execution
  - 支持并行执行

### Key Features / 主要特性

✨ **Task Structure / 任务结构**
  - One atomic change per task
  - 每个任务一个原子变更
  - Testable independently
  - 可独立测试
  - Completable in one session
  - 可在一次会话中完成

✨ **Plan Format / 计划格式**
  ```markdown
  # Plan Title

  ## Summary
  High-level overview

  ## Tasks
  - [ ] Task 1: Description
    - Success criteria
  - [ ] Task 2: Description
  ```

### Example / 示例

```markdown
# Plan: Add User Authentication

## Summary
Implement OAuth authentication with GitHub and Google providers

## Tasks
- [ ] Task 1: Create OAuth controllers
  - Success: POST /auth/github returns JWT token
- [ ] Task 2: Add JWT middleware
  - Success: Protected routes require valid token
- [ ] Task 3: Create user model
  - Success: User can be saved/retrieved from DB
- [ ] Task 4: Write integration tests
  - Success: All tests pass
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Make tasks atomic (one change each)
  - 使任务原子化（每个一个变更）
  - Define clear success criteria
  - 定义清晰的成功标准
  - Order tasks by dependency
  - 按依赖关系排序任务

❌ **DON'T / 避免做法**
  - Group multiple changes in one task
  - 在一个任务中组合多个变更
  - Use vague success criteria
  - 使用模糊的成功标准
  - Skip dependencies
  - 跳过依赖关系

---

## 🤖 Subagent-Driven Development / 子代理驱动开发

> __Quick Access / 快速访问:__ Use for fast iteration with review / 用于快速迭代和审查

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像有个开发助手团队，每个任务派个新助手来做，做完了还要双重检查
**Like having a team of developer assistants, each task gets a fresh assistant with double-checks**

**能做什么 / Capabilities**:
- 每个任务用全新的助手 / Fresh assistant per task
- 两次代码审查（符合计划+代码质量） / Two-stage review
- 在问题变大前发现它 / Catch issues before they compound
- 快速迭代开发 / Fast iteration

**什么时候用 / When to Use**:
- 要执行开发计划时 / Executing development plans
- 需要快速开发时 / Need rapid development
- 项目比较复杂时 / For complex projects
- 想保证质量时 / Want to ensure quality

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

### Purpose / 作用

Execute plans with parallel subagents and two-stage review:
使用并行子代理和双阶段审查执行计划：

- Fresh subagent per task
  - 每个任务使用新的子代理
- Two-stage review process
  - 双阶段审查流程
- Catch issues before they compound
  - 在问题累积前捕获

### Key Features / 主要特性

✨ **Fresh Subagent / 全新子代理**
  - Each task gets fresh context
  - 每个任务获得新上下文
  - No accumulated bias
  - 无累积偏差
  - Clean slate for each task
  - 每个任务都是全新开始

✨ **Two-Stage Review / 双阶段审查**
  1. Spec compliance review (matches plan?)
  2. Code quality review (production-ready?)

### Workflow / 工作流

```
For each task in plan:
  1. Launch fresh subagent
  2. Subagent implements task
  3. Request code review
     a. Spec compliance check
     b. Code quality check
  4. Fix any issues
  5. Mark task complete
  6. Continue to next task
```

### Example / 示例

```
Task: Implement OAuth login

Subagent implements:
- OAuthController with login method
- Error handling
- Logging

Review Stage 1 (Spec Compliance):
✓ Matches plan: OAuth with GitHub/Google
✓ All required fields present

Review Stage 2 (Code Quality):
- Important: Missing input validation
- Minor: Add comments for auth flow

Fix: Add validation, continue
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Review after EVERY task
  - 每个任务后审查
  - Fix issues before proceeding
  - 在继续前修复问题
  - Use fresh subagent each time
  - 每次使用新的子代理

❌ **DON'T / 避免做法**
  - Batch multiple tasks without review
  - 批量处理多个任务而不审查
  - Continue with unfixed issues
  - 在未修复问题的情况下继续
  - Reuse same subagent
  - 重用同一个子代理

---

## 🧪 Test-Driven Development / 测试驱动开发

> __Quick Access / 快速访问:__ Use when writing any code / 编写任何代码时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 先写测试（失败），再写代码（通过），最后优化代码，这三步循环
**Write test (fail) → Write code (pass) → Refactor (improve), repeat this cycle**

**能做什么 / Capabilities**:
- 确保代码真的能工作 / Ensure code really works
- 防止改代码时搞坏功能 / Prevent breaking features
- 让代码更容易维护 / Make code more maintainable
- 提供代码使用示例 / Provide usage examples

**什么时候用 / When to Use**:
- 写任何功能代码时 / Writing any feature code
- 修bug时 / Fixing bugs
- 重构代码时 / Refactoring code
- 基本上任何时候都要写代码 / Basically anytime writing code

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

### Purpose / 作用

Implement code using RED-GREEN-REFACTOR cycle:
使用 RED-GREEN-REFACTOR 循环实现代码：

- Write failing test first
  - 首先编写失败的测试
- Make it pass
  - 使其通过
- Refactor for quality
  - 为质量重构

### Key Features / 主要特性

✨ **RED-GREEN-REFACTOR / 红-绿-重构**

1. **RED / 红**
   - Write test that fails
   - 编写失败的测试
   - Verify it fails with expected error
   - 验证以预期错误失败

2. **GREEN / 绿**
   - Write minimal code to pass
   - 编写最小的通过代码
   - Don't worry about quality yet
   - 还不用担心质量

3. **REFACTOR / 重构**
   - Improve code quality
   - 提高代码质量
   - Keep tests passing
   - 保持测试通过

### Example / 示例

```python
# RED: Write failing test
def test_add_user():
    result = add_user("Alice", "alice@example.com")
    assert result.email == "alice@example.com"
    assert result.id is not None

# Run test - FAILS (function doesn't exist)

# GREEN: Write minimal code
def add_user(name, email):
    user = User(name=name, email=email)
    user.save()
    return user  # Pass test

# Run test - PASSES

# REFACTOR: Improve code
def add_user(name: str, email: str) -> User:
    """Add a new user to the database."""
    if not validate_email(email):
        raise ValueError("Invalid email")
    user = User(name=name, email=email)
    user.save()
    return user

# Run test - STILL PASSES
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - ALWAYS write test first
  - 始终先编写测试
  - Run tests after every change
  - 每次更改后运行测试
  - Keep tests independent
  - 保持测试独立

❌ **DON'T / 避免做法**
  - Write code before tests
  - 在测试之前编写代码
  - Skip RED phase
  - 跳过 RED 阶段
  - Batch multiple features in one test
  - 在一个测试中组合多个功能

---

## ⚡ Executing Plans / 执行计划

> __Quick Access / 快速访问:__ Use when following written plan / 按照书面计划执行时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像批量处理任务，每做完3个任务就停下来检查一下
**Like batch processing tasks, pause to check after every 3 tasks**

**能做什么 / Capabilities**:
- 批量执行任务 / Execute tasks in batches
- 定期检查进度 / Regular progress checks
- 发现问题及时调整 / Adjust when issues found
- 跟踪整体进度 / Track overall progress

**什么时候用 / When to Use**:
- 有书面计划时 / Have written plan
- 任务比较多时 / Many tasks to complete
- 需要定期检查时 / Need periodic checks
- 长时间开发时 / Long development sessions

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

### Purpose / 作用

Execute written plans efficiently with batch processing:
使用批处理高效执行书面计划：

- Process tasks in batches
  - 批量处理任务
- Checkpoints between batches
  - 批次之间的检查点
- Progress tracking
  - 进度跟踪

### Key Features / 主要特性

✨ **Batch Execution / 批量执行**
  - Execute 3 tasks per batch
  - 每批执行 3 个任务
  - Review at checkpoint
  - 在检查点审查
  - Adjust if needed
  - 如需要则调整

✨ **Checkpoint Process / 检查点流程**
  1. Complete batch of tasks
  2. Request code review
  3. Verify against plan
  4. Adjust plan if needed
  5. Continue next batch

### Example / 示例

```
Plan: 9 tasks total

Batch 1 (Tasks 1-3):
  - Execute Task 1 ✓
  - Execute Task 2 ✓
  - Execute Task 3 ✓
  → Checkpoint: Code review
  → Review: Minor issues, ok to continue

Batch 2 (Tasks 4-6):
  - Execute Task 4 ✓
  - Execute Task 5 ✓
  - Execute Task 6 ✓
  → Checkpoint: Code review
  → Review: Important issue in Task 5
  → Fix: Correct Task 5

Batch 3 (Tasks 7-9):
  - Execute Task 7 ✓
  - Execute Task 8 ✓
  - Execute Task 9 ✓
  → Checkpoint: Final review
  → All complete!
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Use checkpoint reviews
  - 使用检查点审查
  - Adjust plan if issues found
  - 如果发现问题调整计划
  - Track progress clearly
  - 清晰跟踪进度

❌ **DON'T / 避免做法**
  - Execute all tasks without checkpoints
  - 在没有检查点的情况下执行所有任务
  - Skip reviews
  - 跳过审查
  - Ignore plan deviations
  - 忽略计划偏差

---

## ✅ Verification Before Completion / 完成前验证

> __Quick Access / 快速访问:__ Use before closing any task/bug / 在关闭任何任务/bug 前使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 关闭bug或任务前，先验证一下真的修好了吗
**Before closing a bug/task, verify it's actually fixed**

**能做什么 / Capabilities**:
- 测试修复是否有效 / Test if fix works
- 验证根本原因已解决 / Verify root cause addressed
- 检查有没有副作用 / Check for side effects
- 防止过早关闭问题 / Prevent premature closure

**什么时候用 / When to Use**:
- 修完bug后 / After fixing bugs
- 完成任务后 / After completing tasks
- 关闭issue前 / Before closing issues
- 任何时候声称"搞定了" / Anytime saying "it's fixed"

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

### Purpose / 作用

Confirm bugs are actually fixed before closing issues:
在关闭问题前确认 bug 真正修复：

- Test the fix
  - 测试修复
- Verify root cause addressed
  - 验证根本原因已解决
- Prevent premature closure
  - 防止过早关闭

### Key Features / 主要特性

✨ **Verification Steps / 验证步骤**
  1. Reproduce original bug
  2. Apply fix
  3. Verify fix works
  4. Check for side effects
  5. Close issue

### Example / 示例

```
Bug: "Login fails with special characters in password"

Fix Applied: Added password encoding

Verification:
1. ✓ Reproduce bug: Login fails with "p@ss!123"
2. ✓ Apply fix: Add base64 encoding
3. ✓ Test fix: Login now works
4. ✓ Side effects: Normal passwords still work
5. ✓ Close issue: VERIFIED
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Test with original scenario
  - 使用原始场景测试
  - Check for edge cases
  - 检查边缘情况
  - Verify no regressions
  - 验证没有回归

❌ **DON'T / 避免做法**
  - Close without testing
  - 在没有测试的情况下关闭
  - Assume fix works
  - 假设修复有效
  - Ignore edge cases
  - 忽略边缘情况

---

## 🎬 Finishing Development Branch / 完成开发分支

> __Quick Access / 快速访问:__ Use when ready to merge / 准备合并时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 功能做完了，要合并到主分支了，有三种处理方式
**Feature is done, time to merge to main branch, three ways to handle it**

**能做什么 / Capabilities**:
- 直接合并（简单改动） / Direct merge (simple changes)
- 创建PR（需要审查） / Create PR (needs review)
- 丢弃分支（实验失败） / Discard branch (experiment failed)

**什么时候用 / When to Use**:
- 功能开发完成时 / Feature development complete
- 准备合并代码时 / Ready to merge code
- 实验不需要时 / Experiment not needed
- 分支太乱需要清理时 / Branch too messy, need cleanup

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

### Purpose / 作用

Properly complete development branches with:
正确完成开发分支：

- Clean merge to main
  - 清理合并到 main
- Or create pull request
  - 或创建 pull request
- Or discard if needed
  - 或需要时丢弃

### Key Features / 主要特性

✨ **Three Paths / 三种路径**

1. **Merge Directly / 直接合并**
   - Small, simple changes
   - 小而简单的更改
   - Well-tested
   - 经过良好测试
   - Low risk
   - 低风险

2. **Pull Request / Pull 请求**
   - Larger changes
   - 较大的更改
   - Needs review
   - 需要审查
   - Collaborative
   - 协作性

3. **Discard / 丢弃**
   - Experiment failed
   - 实验失败
   - Better approach found
   - 找到更好的方法
   - No longer needed
   - 不再需要

### Example / 示例

```
Branch: feature/user-auth

Status: All tasks complete, tests pass

Decision: Create PR

Steps:
1. ✓ Update branch from main
2. ✓ Run full test suite
3. ✓ Create PR with description
4. ✓ Link to plan/issues
5. ✓ Request review
6. ✓ Address review feedback
7. ✓ Merge after approval

Alternative: Discard if experiment failed
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Ensure all tests pass
  - 确保所有测试通过
  - Update from main first
  - 首先从 main 更新
  - Write clear PR descriptions
  - 编写清晰的 PR 描述

❌ **DON'T / 避免做法**
  - Merge with failing tests
  - 在测试失败的情况下合并
  - Skip documentation
  - 跳过文档
  - Leave dead branches
  - 留下死分支

---

## 👁️ Requesting Code Review / 请求代码审查

> __Quick Access / 快速访问:__ Use after each task or feature / 在每个任务或功能后使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 写完代码后，请别人（或另一个AI）帮你检查一下有什么问题
**After writing code, ask someone (or another AI) to check for problems**

**能做什么 / Capabilities**:
- 系统化的代码审查 / Systematic code review
- 两阶段检查（符合计划+代码质量） / Two-stage check
- 在问题变严重前发现 / Catch issues before they compound
- 获取改进建议 / Get improvement suggestions

**什么时候用 / When to Use**:
- 完成任务后 / After completing tasks
- 完成功能后 / After completing features
- 合并代码前 / Before merging code
- 被卡住时 / When stuck

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

### Purpose / 作用

Get systematic code reviews to catch issues early:
获得系统化的代码审查以尽早捕获问题：

- Pre-review checklist
  - 预审查检查清单
- Two-stage review process
  - 双阶段审查流程
- Catch issues before they compound
  - 在问题累积前捕获

### Key Features / 主要特性

✨ **When to Review / 审查时机**

**Mandatory / 必须的:**
- After each task in subagent-driven development
  - 子代理驱动开发中的每个任务后
- After completing major feature
  - 完成主要功能后
- Before merge to main
  - 合并到 main 前

**Optional but valuable / 可选但有价值:**
- When stuck (fresh perspective)
  - 卡住时（新视角）
- Before refactoring (baseline check)
  - 重构前（基线检查）
- After fixing complex bug
  - 修复复杂 bug 后

✨ **How to Request / 如何请求**

```bash
# 1. Get git SHAs
BASE_SHA=$(git rev-parse HEAD~1)
HEAD_SHA=$(git rev-parse HEAD)

# 2. Dispatch code-reviewer subagent
# 3. Fill template with:
#    - What was implemented
#    - Plan/requirements
#    - BASE_SHA and HEAD_SHA
#    - Brief description

# 4. Act on feedback
#    - Fix Critical issues immediately
#    - Fix Important issues before proceeding
#    - Note Minor issues for later
```

### Example / 示例

```
Just completed: Task 2 - Add verification function

Request code review:
  WHAT: Verification and repair functions
  PLAN: Task 2 from deployment-plan.md
  BASE_SHA: a7981ec
  HEAD_SHA: 3df7661
  DESC: Added verifyIndex() and repairIndex()

Review returns:
  Strengths: Clean architecture, real tests
  Issues:
    Important: Missing progress indicators
    Minor: Magic number (100)
  Assessment: Ready to proceed

Action: Fix progress indicators, continue
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Review early and often
  - 早审查常审查
  - Fix Critical/Important issues
  - 修复关键/重要问题
  - Push back with reasoning if wrong
  - 如果错误用推理反驳

❌ **DON'T / 避免做法**
  - Skip review for "simple" code
  - 跳过"简单"代码的审查
  - Ignore Critical issues
  - 忽略关键问题
  - Proceed with unfixed Important issues
  - 在未修复重要问题的情况下继续

---

## 📥 Receiving Code Review / 接收代码审查

> __Quick Access / 快速访问:__ Use when responding to feedback / 响应反馈时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 别人审查你的代码提意见了，你要建设性地回应
**Someone reviewed your code and gave feedback, respond constructively**

**能做什么 / Capabilities**:
- 技术性评价（不是盲目同意） / Technical evaluation (not blind agreement)
- 错的时候可以反驳 / Push back when wrong
- 对的时候学习改进 / Learn and improve when right
- 保持专业态度 / Maintain professional attitude

**什么时候用 / When to Use**:
- 收到代码审查反馈后 / After receiving review feedback
- 需要回应建议时 / When need to respond to suggestions
- 不确定建议是否正确时 / Unsure if suggestion is correct
- 需要讨论技术方案时 / When need to discuss technical approach

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

### Purpose / 作用

Respond constructively to code review feedback:
建设性地回应代码审查反馈：

- Technical evaluation over performative agreement
  - 技术性评价而非表演性同意
- Push back when wrong
  - 错误时反驳
- Learn from feedback
  - 从反馈中学习

### Key Features / 主要特性

✨ **Response Principles / 回应原则**

1. **Evaluate Technical Merit / 评估技术优点**
   - Is feedback technically correct?
   - 反馈在技术上是否正确？
   - Does it improve the code?
   - 它是否改进了代码？
   - Or is it subjective?
   - 还是主观的？

2. **Push Back When Appropriate / 适当时反驳**
   - Use technical reasoning
   - 使用技术推理
   - Show tests proving it works
   - 显示证明其有效的测试
   - Explain trade-offs
   - 解释权衡

3. **Accept When Right / 正确时接受**
   - Fix the issue
   - 修复问题
   - Learn from it
   - 从中学习
   - Apply to future code
   - 应用于未来代码

### Example / 示例

```
Reviewer: "Use async/await instead of promises"

Analysis:
- Current code uses .then() chains
- Works correctly, passes all tests
- Async/await would be more readable

Decision: ACCEPT
Action: Refactor to async/await
Learning: Prefer async/await for new code
```

```
Reviewer: "Remove console.log statements"

Analysis:
- These are intentional debug logs
- Help troubleshoot production issues
- Documented in README

Decision: PUSH BACK
Reasoning:
- Logs are production-debugging tool
- Not accidental debug statements
- Covered in documentation
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Evaluate feedback technically
  - 技术性地评估反馈
  - Push back when wrong
  - 错误时反驳
  - Learn from valid feedback
  - 从有效反馈中学习

❌ **DON'T / 避免做法**
  - Accept everything blindly
  - 盲目接受一切
  - Take feedback personally
  - 个人化反馈
  - Argue without reasoning
  - 没有推理地争论

---

## 🚀 Dispatching Parallel Agents / 调度并行子代理

> __Quick Access / 快速访问:__ Use for independent problem-solving / 用于独立问题解决

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 同时派几个AI助手分别解决同一个问题，然后比较结果选最好的
**Dispatch multiple AI assistants to solve same problem simultaneously, compare results**

**能做什么 / Capabilities**:
- 并发解决问题 / Concurrent problem solving
- 获得不同视角 / Get different perspectives
- 探索多种方案 / Explore multiple approaches
- 更快迭代 / Faster iteration

**什么时候用 / When to Use**:
- 有多个独立问题时 / Multiple independent problems
- 需要探索方案时 / Exploring alternatives
- 不确定哪种方法好时 / Unsure which approach is best
- 需要新思路时 / Need fresh perspectives

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

### Purpose / 作用

Run multiple subagents in parallel for independent tasks:
为独立任务并行运行多个子代理：

- Concurrent problem solving
  - 并发问题解决
- Faster iteration
  - 更快的迭代
- Independent results
  - 独立结果

### Key Features / 主要特性

✨ **When to Use / 何时使用**

- Multiple independent problems
  - 多个独立问题
- No shared dependencies
  - 无共享依赖
- Need fresh perspectives
  - 需要新视角
- Exploring alternatives
  - 探索替代方案

✨ **How to Dispatch / 如何调度**

```python
# Launch multiple agents in parallel
agents = []
for problem in problems:
    agent = launch_agent(
        task=solve_problem,
        context=problem,
        independent=True
    )
    agents.append(agent)

# Collect all results
results = [agent.wait() for agent in agents]
```

### Example / 示例

```
Problem: "Optimize slow database queries"

Approach 1 Agent:
- Analyzes query execution plans
- Proposes indexing strategy
- Estimates improvement

Approach 2 Agent:
- Reviews query structure
- Proposes refactoring approach
- Estimates effort

Approach 3 Agent:
- Researches caching options
- Proposes Redis integration
- Estimates complexity

Compare results, choose best approach
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Ensure tasks are truly independent
  - 确保任务真正独立
  - Give each agent full context
  - 给每个代理完整上下文
  - Compare results objectively
  - 客观比较结果

❌ **DON'T / 避免做法**
  - Use for dependent tasks
  - 用于依赖任务
  - Share context between agents
  - 在代理间共享上下文
  - Launch too many (limit to 3-4)
  - 启动太多（限制在 3-4 个）

---

## 🌳 Using Git Worktrees / 使用 Git Worktrees

> __Quick Access / 快速访问:__ Use for parallel development / 用于并行开发

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 同一个仓库可以有好几个工作目录，同时在不同分支上工作
**Same repo can have multiple working directories, work on different branches simultaneously**

**能做什么 / Capabilities**:
- 同时开发多个功能 / Work on multiple features simultaneously
- 热修复时不打断功能开发 / Hotfix without interrupting feature work
- 轻松切换上下文 / Easy context switching
- 避免频繁 stash/pop / Avoid frequent stash/pop

**什么时候用 / When to Use**:
- 同时做多件事时 / Doing multiple things at once
- 紧急修复时 / Emergency fixes
- 测试不同方案时 / Testing different approaches
- 审查代码时还在开发 / Reviewing code while developing

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

### Purpose / 作用

Work on multiple branches simultaneously without context switching:
同时处理多个分支而无需上下文切换：

- Parallel development
  - 并行开发
- Isolated working trees
  - 隔离的工作树
- Easy context switching
  - 简单的上下文切换

### Key Features / 主要特性

✨ **What are Worktrees / 什么是 Worktrees**

Multiple working directories for different branches:
不同分支的多个工作目录：

```
project/              # Main branch
project-feature-a/    # Feature A branch
project-feature-b/    # Feature B branch
project-bugfix/       # Bugfix branch
```

✨ **When to Use / 何时使用**

- Working on multiple features simultaneously
  - 同时处理多个功能
- Hotfix needed while feature in progress
  - 功能进行中需要热修复
- Testing multiple approaches
  - 测试多种方法
- Code review while working
  - 工作时进行代码审查

### Example / 示例

```bash
# Create worktree for new feature
git worktree add ../project-feature-a feature-a

# Now have two directories:
# project/        (main branch)
# project-feature-a/ (feature-a branch)

# Work in feature-a
cd ../project-feature-a
# Make changes, commit

# Switch back to main anytime
cd ../project
# No stash/pop needed!

# Remove worktree when done
git worktree remove ../project-feature-a
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Use for truly parallel work
  - 用于真正的并行工作
  - Name worktrees clearly
  - 清晰命名 worktrees
  - Remove when done
  - 完成后删除

❌ **DON'T / 避免做法**
  - Create too many (hard to manage)
  - 创建太多（难以管理）
  - Forget to remove
  - 忘记删除
  - Use for sequential work
  - 用于顺序工作

---

## 🔍 Systematic Debugging / 系统化调试

> __Quick Access / 快速访问:__ Use when investigating bugs / 调查 bug 时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 有条理地排查bug，而不是瞎改代码碰运气
**Debug bugs methodically instead of randomly changing code**

**能做什么 / Capabilities**:
- 系统化调查问题 / Systematic investigation
- 找到根本原因 / Find root cause
- 验证假设 / Test hypotheses
- 记录发现 / Document findings

**什么时候用 / When to Use**:
- 发现bug时 / When bugs are found
- 不知道怎么修时 / Don't know how to fix
- bug很复杂时 / Complex bugs
- 需要理解问题时 / Need to understand the problem

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

### Purpose / 作用

Structure debugging process to find root cause efficiently:
结构化调试流程以高效找到根本原因：

- Systematic investigation
  - 系统化调查
- Root cause analysis
  - 根本原因分析
- Documented findings
  - 记录发现

### Key Features / 主要特性

✨ **Debugging Process / 调试流程**

1. **Understand the Problem / 理解问题**
   - Reproduce the bug
   - 重现 bug
   - Gather context
   - 收集上下文

2. **Form Hypothesis / 形成假设**
   - What could cause this?
   - 什么可能导致这个？
   - Rank by likelihood
   - 按可能性排序

3. **Test Hypothesis / 测试假设**
   - Create minimal reproduction
   - 创建最小重现
   - Test each hypothesis
   - 测试每个假设

4. **Fix and Verify / 修复和验证**
   - Implement fix
   - 实施修复
   - Verify root cause addressed
   - 验证根本原因已解决

### Example / 示例

```
Bug: "User login fails intermittently"

1. Understand:
   - Reproduces ~10% of time
   - Only with specific password pattern
   - No error messages

2. Hypothesis:
   - H1: Race condition in auth
   - H2: Password encoding issue
   - H3: Database connection timeout

3. Test:
   - Test H1: Add delays - no effect
   - Test H2: Log encoding -发现 special chars fail
   - H2 CONFIRMED

4. Fix:
   - Add proper escaping for special chars
   - Verify: 100 login attempts, all succeed
```

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Reproduce bug first
  - 首先重现 bug
  - Form specific hypotheses
  - 形成具体的假设
  - Test one thing at a time
  - 一次测试一件事
  - Document findings
  - 记录发现

❌ **DON'T / 避免做法**
  - Randomly change code
  - 随机更改代码
  - Skip to fix without understanding
  - 在不理解的情况下跳到修复
  - Ignore root cause
  - 忽略根本原因

---

## 📘 Using Superpowers / Superpowers 使用指南

> __Quick Access / 快速访问:__ Meta-skill for using all skills / 使用所有技能的元技能

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 教你怎么用这些技能的说明书
**Manual on how to use all these skills**

**能做什么 / Capabilities**:
- 技能调用规则 / Skill invocation rules
- 危险信号警示 / Red flags to watch for
- 最佳实践建议 / Best practices
- 完整工作流程 / Complete workflow

**什么时候用 / When to Use**:
- 第一次使用技能时 / First time using skills
- 不清楚用哪个技能时 / Unsure which skill to use
- 想了解最佳实践时 / Want to learn best practices
- 遇到问题时 / When encountering problems

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

### Purpose / 作用

Learn when and how to use all Superpowers skills:
学习何时以及如何使用所有 Superpowers 技能：

- Skill invocation rules
  - 技能调用规则
- Red flags to watch for
  - 要注意的危险信号
- Best practices
  - 最佳实践

### Key Features / 主要特性

✨ **Skill Invocation / 技能调用**

**Automatic / 自动:**
- Skills auto-invoke based on context
  - 技能根据上下文自动调用
- Just describe what you need
  - 只需描述你的需求

**Manual / 手动:**
- Use `/skill-name` syntax
  - 使用 `/skill-name` 语法
- Explicitly request specific skill
  - 显式请求特定技能

✨ **Red Flags / 危险信号**

❌ **Never / 从不:**
- Skip code review skills
  - 跳过代码审查技能
- Ignore brainstorming for complex tasks
  - 忽略复杂任务的头脑风暴
- Use TDD incorrectly (write code first)
  - 错误使用 TDD（先写代码）

### Skill Workflow / 技能工作流

```
Idea → brainstorming → writing-plans →
subagent-driven-development →
  test-driven-development →
  requesting-code-review →
verification-before-completion →
finishing-a-development-branch
```

---

## ✍️ Writing Skills / 编写技能

> __Quick Access / 快速访问:__ Use when creating new skills / 创建新技能时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 用TDD的方法来写技能文档，先测试再写文档
**Write skill documentation using TDD: test first, then document**

**能做什么 / Capabilities**:
- 先用再写 / Test before documenting
- 真实场景验证 / Validate with real usage
- 迭代改进文档 / Iterate on documentation
- 确保文档准确 / Ensure documentation accuracy

**什么时候用 / When to Use**:
- 创建新技能时 / Creating new skills
- 改进现有技能时 / Improving existing skills
- 技能文档过时时 / When documentation is outdated
- 分享技能给他人时 / Sharing skills with others

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

### Purpose / 作用

Apply TDD principles to skill documentation:
将 TDD 原则应用于技能文档：

- Test skills before documenting
  - 在文档化之前测试技能
- Validate with real usage
  - 通过真实使用验证
- Iterate on documentation
  - 迭代文档

### Key Features / 主要特性

✨ **TDD for Documentation / 文档的 TDD**

1. **RED / 红**
   - Use skill in real scenarios
   - 在真实场景中使用技能
   - Identify what's missing
   - 识别缺失内容

2. **GREEN / 绿**
   - Write documentation
   - 编写文档
   - Cover identified gaps
   - 覆盖识别的差距

3. **REFACTOR / 重构**
   - Improve clarity
   - 提高清晰度
   - Add examples
   - 添加示例
   - Refine structure
   - 完善结构

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Test skills before writing
  - 在编写前测试技能
  - Use real examples
  - 使用真实示例
  - Iterate based on usage
  - 根据使用迭代

❌ **DON'T / 避免做法**
  - Write without testing
  - 在没有测试的情况下编写
  - Use theoretical examples
  - 使用理论示例
  - Skip user feedback
  - 跳过用户反馈

---

## 📊 Summary / 总结

### Complete Development Workflow / 完整开发工作流

```
1. 💡 Idea
   → brainstorming

2. 📋 Plan
   → writing-plans

3. 🚀 Implement
   → subagent-driven-development
   → test-driven-development
   → systematic-debugging (if bugs)

4. 👁️ Review
   → requesting-code-review
   → receiving-code-review

5. ✅ Verify
   → verification-before-completion

6. 🎬 Finish
   → finishing-a-development-branch
```

### Key Principles / 关键原则

✨ **Quality First / 质量优先**
  - Test-driven development
  - 测试驱动开发
  - Code reviews at every stage
  - 每个阶段代码审查
  - Verification before completion
  - 完成前验证

✨ **Systematic Approach / 系统化方法**
  - Plan before coding
  - 编码前计划
  - Debug systematically
  - 系统化调试
  - Document decisions
  - 记录决策

✨ **Continuous Improvement / 持续改进**
  - Learn from reviews
  - 从审查中学习
  - Refactor regularly
  - 定期重构
  - Share knowledge
  - 分享知识

---

## 🔗 Resources / 资源

- 📖 [obra/superpowers Repository](https://github.com/obra/superpowers)
- 📖 [Claude Code Documentation](https://docs.anthropic.com/claude-code)

---

_💡 Tip: Combine multiple skills for complete development workflow / 提示：组合多个技能以实现完整的开发工作流_
