# 🌐 Web Development Skills Guide / Web 开发技能指南

## 🌐 Web 开发技能指南

> __Official Sources / 官方来源:__
> Based on anthropics/skills repository
> 基于 anthropics/skills 仓库

---

## 📋 Overview / 概述

Web development skills provide tools for designing, building, and testing modern web applications using React, Tailwind CSS, and Playwright.

Web 开发技能提供使用 React、Tailwind CSS 和 Playwright 设计、构建和测试现代 Web 应用程序的工具。

本指南涵盖了：
- **Frontend Design / 前端设计** - UI/UX with React & Tailwind
- **Web Artifacts Builder / Web 构件构建器** - React + Tailwind HTML artifacts
- **WebApp Testing / Web 应用测试** - Playwright testing framework

---

## 💻 Frontend Design / 前端 UI/UX 设计

> __Quick Access / 快速访问:__ Use when designing UI/UX / 设计 UI/UX 时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像个UI/UX设计师,用React和Tailwind设计现代化的用户界面
**Like a UI/UX designer that creates modern user interfaces with React and Tailwind**

**能做什么 / Capabilities**:
- 设计响应式组件 / Design responsive components
- 应用现代样式 / Apply modern styles
- 确保可访问性 / Ensure accessibility
- 快速原型开发 / Rapid prototyping

**什么时候用 / When to Use**:
- 创建Web应用界面时 / Creating web app interfaces
- 设计响应式布局时 / Designing responsive layouts
- 需要现代化UI时 / Need modern UI
- 快速原型验证时 / Rapid prototype validation

**怎么用 / How to Use**:
```
告诉 Claude："帮我设计这个页面"
Tell Claude: "Help me design this page"

Claude 会使用 frontend-design 技能
创建 React + Tailwind 组件
Create React + Tailwind components
```

**举例 / Example**:
```
你说："设计一个登录页面"

技能会：
1️⃣ 创建响应式布局
2️⃣ 设计表单组件
3️⃣ 应用现代化样式
4️⃣ 添加交互效果
5️⃣ 确保可访问性

结果：专业、美观、可用的登录界面!
```

### Purpose / 作用

Design modern UI/UX with React and Tailwind CSS:
使用 React 和 Tailwind CSS 设计现代 UI/UX：

- Component-based design
  - 基于组件的设计
- Responsive layouts
  - 响应式布局
- Modern styling
  - 现代样式

### Key Features / 主要特性

✨ **Component Design / 组件设计**
  - Reusable components
  - 可重用组件
  - Props and state
  - 属性和状态
  - Composition
  - 组合

✨ **Styling / 样式**
  - Tailwind utility classes
  - Tailwind 工具类
  - Custom themes
  - 自定义主题
  - Responsive design
  - 响应式设计

### Example / 示例

```jsx
import React, { useState } from 'react';

function LoginForm() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-purple-50 flex items-center justify-center">
      <div className="bg-white p-8 rounded-lg shadow-xl w-96">
        <h2 className="text-2xl font-bold text-gray-900 mb-6">Login</h2>

        <form className="space-y-4">
          <div>
            <label className="block text-sm font-medium text-gray-700 mb-1">
              Email
            </label>
            <input
              type="email"
              value={email}
              onChange={(e) => setEmail(e.target.value)}
              className="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
            />
          </div>

          <div>
            <label className="block text-sm font-medium text-gray-700 mb-1">
              Password
            </label>
            <input
              type="password"
              value={password}
              onChange={(e) => setPassword(e.target.value)}
              className="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
            />
          </div>

          <button
            type="submit"
            className="w-full bg-blue-500 text-white py-2 rounded-md hover:bg-blue-600 transition"
          >
            Sign In
          </button>
        </form>
      </div>
    </div>
  );
}
```

### Best Practices / 最佳实践

✅ Use semantic HTML / 使用语义化 HTML
✅ Ensure accessibility / 确保可访问性
✅ Design mobile-first / 移动优先设计
❌ Avoid inline styles / 避免内联样式
❌ Don't ignore responsive design / 不要忽略响应式设计

---

## 🎨 Web Artifacts Builder / Web 构件构建器

> __Quick Access / 快速访问:__ Use when creating HTML artifacts / 创建 HTML 构件时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像个前端构建专家,用现代工具创建精美的HTML构件
**Like a frontend build expert that creates elaborate HTML artifacts with modern tools**

**能做什么 / Capabilities**:
- 使用Vite构建 / Build with Vite
- React组件开发 / React component development
- Tailwind样式 / Tailwind styling
- 生产就绪的输出 / Production-ready output

**什么时候用 / When to Use**:
- 创建HTML构件时 / Creating HTML artifacts
- 需要独立运行的应用时 / Need standalone apps
- 快速原型验证时 / Rapid prototype validation
- 分享Demo时 / Sharing demos

**怎么用 / How to Use**:
```
告诉 Claude："创建一个Web构件"
Tell Claude: "Create a web artifact"

Claude 会使用 web-artifacts-builder 技能
Claude will use web-artifacts-builder skill
```

**举例 / Example**:
```
你说："创建一个数据可视化面板"

技能会：
1️⃣ 搭建Vite + React项目
2️⃣ 配置Tailwind CSS
3️⃣ 创建数据组件
4️⃣ 添加交互功能
5️⃣ 优化构建输出

结果：可部署的、性能优异的Web应用!
```

### Purpose / 作用

Create elaborate HTML artifacts with modern tools:
使用现代工具创建精美的 HTML 构件：

- React components
  - React 组件
- Tailwind CSS styling
  - Tailwind CSS 样式
- Production-ready builds
  - 生产就绪的构建

### Key Features / 主要特性

✨ **Tech Stack / 技术栈**
  - React for components
  - Vite for building
  - Tailwind for styling

✨ **Features / 功能**
  - Fast development
  - 快速开发
  - Optimized production builds
  - 优化的生产构建
  - TypeScript support
  - TypeScript 支持

### Example / 示例

```bash
# Create new artifact
npm create vite@latest artifact -- --template react-ts
cd artifact
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

```jsx
// App.jsx
function Artifact() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-purple-50 p-8">
      <div className="max-w-4xl mx-auto bg-white rounded-lg shadow-xl p-8">
        <h1 className="text-4xl font-bold text-gray-900 mb-4">
          Artifact Title
        </h1>
        <p className="text-lg text-gray-700">
          Artifact content goes here...
        </p>
      </div>
    </div>
  );
}
```

### Best Practices / 最佳实践

✅ Use component-based architecture / 使用基于组件的架构
✅ Optimize for performance / 优化性能
✅ Ensure accessibility / 确保可访问性

---

## 🧪 WebApp Testing / Web 应用测试

> __Quick Access / 快速访问:__ Use when testing web applications / 测试 Web 应用时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 像个测试工程师,用Playwright自动测试Web应用是否正常工作
**Like a test engineer that uses Playwright to automatically test if web apps work correctly**

**能做什么 / Capabilities**:
- 自动化浏览器测试 / Automated browser testing
- 跨浏览器测试 / Cross-browser testing
- 视觉回归测试 / Visual regression testing
- 端到端测试 / End-to-end testing

**什么时候用 / When to Use**:
- 开发Web应用时 / Developing web apps
- 需要自动化测试时 / Need automated testing
- 确保多浏览器兼容时 / Ensuring cross-browser compatibility
- 防止回归bug时 / Preventing regression bugs

**怎么用 / How to Use**:
```
告诉 Claude："测试这个应用"
Tell Claude: "Test this application"

Claude 会使用 webapp-testing 技能
Claude will use webapp-testing skill
```

**举例 / Example**:
```
你有：一个电商网站

技能会：
1️⃣ 编写Playwright测试
2️⃣ 测试登录流程
3️⃣ 测试购物车功能
4️⃣ 测试结账流程
5️⃣ 在Chrome、Firefox、Safari中运行

结果：确保所有功能在所有浏览器中都正常工作!
```

### Purpose / 作用

Test web applications using Playwright:
使用 Playwright 测试 Web 应用：

- Automated testing
  - 自动化测试
- Cross-browser support
  - 跨浏览器支持
- Visual regression testing
  - 视觉回归测试

### Key Features / 主要特性

✨ **Browser Support / 浏览器支持**
  - Chromium
  - Firefox
  - WebKit

✨ **Testing Capabilities / 测试能力**
  - Click buttons
  - Fill forms
  - Navigate pages
  - Take screenshots

### Dependencies / 依赖

```bash
npm install -D @playwright/test
npx playwright install
```

### Example / 示例

```javascript
import { test, expect } from '@playwright/test';

test('homepage loads', async ({ page }) => {
  await page.goto('http://localhost:3000');

  // Check title
  await expect(page).toHaveTitle(/My App/);

  // Check element
  await expect(page.locator('h1')).toContainText('Welcome');

  // Check interaction
  await page.click('button#submit');
  await expect(page.locator('.success')).toBeVisible();
});

test('login flow', async ({ page }) => {
  await page.goto('http://localhost:3000/login');

  // Fill form
  await page.fill('input[name="email"]', 'user@example.com');
  await page.fill('input[name="password"]', 'password123');

  // Submit
  await page.click('button[type="submit"]');

  // Verify
  await expect(page).toHaveURL(/.*dashboard/);
});
```

### Best Practices / 最佳实践

✅ Use data-testid selectors / 使用 data-testid 选择器
✅ Wait for elements before acting / 在操作前等待元素
✅ Test user flows, not implementation / 测试用户流程而非实现
❌ Don't use brittle selectors / 不要使用脆弱的选择器

---

## 📊 Summary / 总结

### Web Development Workflow / Web 开发工作流

```
Design UI/UX → Build Components → Test Application → Deploy
  ↓              ↓                 ↓              ↓
Frontend    Web Artifacts     WebApp Testing  Production
Design      Builder
```

### Key Principles / 关键原则

✨ **Modern Stack / 现代技术栈**
  - React for components
  - Tailwind for styling
  - Playwright for testing

✨ **Best Practices / 最佳实践**
  - Component-based design
  - Automated testing
  - Accessibility first

---

## 🔗 Resources / 资源

- 📖 [React Documentation](https://react.dev/)
- 📖 [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- 📖 [Playwright Documentation](https://playwright.dev/docs)

---

_💡 Tip: Test responsive design at different viewport sizes / 提示：在不同视口大小测试响应式设计_
