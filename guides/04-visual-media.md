# 🎨 Visual & Media Skills Guide / 视觉媒体技能指南

## 🎨 视觉媒体技能指南

> __Official Sources / 官方来源:__
> Based on anthropics/skills repository
> 基于 anthropics/skills 仓库

---

## 📋 Overview / 概述

Visual and media skills enable creation of generative art, animations, and professional themes for visual content.

视觉媒体技能能够创建生成艺术、动画和专业主题的视觉内容。

本指南涵盖了：
- **Algorithmic Art / 算法艺术** - Generative art creation / 生成艺术创建
- **Canvas Design / Canvas 设计** - HTML5 Canvas visual art / Canvas 视觉艺术
- **Slack GIF Creator / Slack GIF 创建器** - Animated GIFs for Slack / Slack 优化的 GIF 动画
- **Theme Factory / 主题工厂** - 10 professional themes / 10 个专业主题

---

## 🎨 Algorithmic Art / 算法艺术

> __Quick Access / 快速访问:__ Use when creating generative art / 创建生成艺术时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 用算法和数学模式自动生成艺术作品
**Use algorithms and mathematical patterns to automatically generate art**

**能做什么 / Capabilities**:
- 程序化生成图像 / Procedurally generate images
- 创建数学模式 / Create mathematical patterns
- 随机艺术创作 / Random art creation
- 动画和交互 / Animation and interaction

**什么时候用 / When to Use**:
- 创作数字艺术时 / Creating digital art
- 生成纹理和图案时 / Generating textures and patterns
- 创意编程时 / Creative coding
- 探索生成艺术时 / Exploring generative art

**怎么用 / How to Use**:
```
告诉 Claude："创建一些算法艺术"
Tell Claude: "Create some algorithmic art"

Claude 会使用 algorithmic-art 技能
Claude will use algorithmic-art skill
```

**举例 / Example**:
```
你说："生成一些抽象艺术"

技能会：
1️⃣ 使用Perlin噪声生成纹理
2️⃣ 创建分形图案
3️⃣ 随机生成形状和颜色
4️⃣ 组合多种技术
5️⃣ 输出高质量图像

结果：独一无二的数字艺术作品!
```

### Purpose / 作用

Create art using algorithms and mathematical patterns:
使用算法和数学模式创建艺术：

- Procedural generation
  - 程序化生成
- Mathematical patterns
  - 数学模式
- Randomness with control
  - 受控的随机性

### Key Features / 主要特性

✨ **Generative Techniques / 生成技术**
  - Perlin noise
  - Fractal patterns
  - L-systems
  - Particle systems

✨ **Output Formats / 输出格式**
  - Static images
  - Animations
  - Interactive art

### Example / 示例

```python
import random
from PIL import Image, ImageDraw

def generate_art(width, height):
    img = Image.new('RGB', (width, height), (240, 248, 255))
    draw = ImageDraw.Draw(img)

    # Generate random circles
    for _ in range(50):
        x = random.randint(0, width)
        y = random.randint(0, height)
        r = random.randint(10, 50)
        color = (
            random.randint(50, 200),
            random.randint(50, 200),
            random.randint(100, 250)
        )
        draw.ellipse([x-r, y-r, x+r, y+r], fill=color, outline=None)

    return img

art = generate_art(800, 600)
art.save('generative_art.png')
```

### Best Practices / 最佳实践

✅ Experiment with parameters / 实验参数
✅ Use seed for reproducibility / 使用种子以实现可重现性
✅ Combine multiple techniques / 组合多种技术

---

## 🖼️ Canvas Design / Canvas 视觉艺术

> __Quick Access / 快速访问:__ Use when creating HTML5 Canvas art / 创建 Canvas 艺术时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 使用HTML5 Canvas创建交互式图形和动画
**Use HTML5 Canvas to create interactive graphics and animations**

**能做什么 / Capabilities**:
- 绘制形状和路径 / Draw shapes and paths
- 创建动画效果 / Create animations
- 复杂可视化 / Complex visualizations
- 交互式图形 / Interactive graphics

**什么时候用 / When to Use**:
- 创建数据可视化时 / Creating data visualizations
- 开发互动图形时 / Developing interactive graphics
- 需要高性能渲染时 / Need high-performance rendering
- 创建动画效果时 / Creating animations

**怎么用 / How to Use**:
```
告诉 Claude："用Canvas创建一个视觉效果"
Tell Claude: "Create a visual effect using Canvas"

Claude 会使用 canvas-design 技能
Claude will use canvas-design skill
```

**举例 / Example**:
```
你说："创建一个动态背景效果"

技能会：
1️⃣ 设置Canvas元素
2️⃣ 编写渲染循环
3️⃣ 添加渐变和动画
4️⃣ 优化性能
5️⃣ 处理高DPI显示器

结果：流畅、美观的动画背景!
```

### Purpose / 作用

Create visual art using HTML5 Canvas:
使用 HTML5 Canvas 创建视觉艺术：

- Interactive graphics
  - 交互式图形
- Animations
  - 动画
- Complex visualizations
  - 复杂可视化

### Key Features / 主要特性

✨ **Drawing Capabilities / 绘图能力**
  - Shapes and paths
  - 形状和路径
  - Gradients and patterns
  - 渐变和图案
  - Text and images
  - 文本和图像

✨ **Animation / 动画**
  - requestAnimationFrame
  - Frame-by-frame control
  - Smooth transitions

### Example / 示例

```html
<canvas id="artCanvas" width="800" height="600"></canvas>

<script>
const canvas = document.getElementById('artCanvas');
const ctx = canvas.getContext('2d');

// Draw animated gradient
function animate() {
    const time = Date.now() * 0.001;

    // Create gradient
    const gradient = ctx.createLinearGradient(0, 0, canvas.width, canvas.height);
    gradient.addColorStop(0, `hsl(${time * 50}, 70%, 50%)`);
    gradient.addColorStop(1, `hsl(${time * 50 + 60}, 70%, 50%)`);

    // Fill canvas
    ctx.fillStyle = gradient;
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Draw animated circles
    for (let i = 0; i < 5; i++) {
        ctx.beginPath();
        const x = canvas.width/2 + Math.cos(time + i) * 100;
        const y = canvas.height/2 + Math.sin(time + i) * 100;
        ctx.arc(x, y, 30, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(255, 255, 255, 0.5)`;
        ctx.fill();
    }

    requestAnimationFrame(animate);
}

animate();
</script>
```

### Best Practices / 最佳实践

✅ Optimize rendering performance / 优化渲染性能
✅ Use offscreen canvas for complex operations / 对复杂操作使用离屏 canvas
✅ Handle high DPI displays / 处理高 DPI 显示器

---

## 🎞️ Slack GIF Creator / Slack 优化的 GIF 动画

> __Quick Access / 快速访问:__ Use when creating GIFs for Slack / 为 Slack 创建 GIF 时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 创建专门为Slack优化的动画GIF表情和图片
**Create animated GIFs and images optimized specifically for Slack**

**能做什么 / Capabilities**:
- 创建Slack尺寸的GIF / Create Slack-sized GIFs
- 优化文件大小 / Optimize file size
- 流畅动画效果 / Smooth animations
- Emoji和消息GIF / Emoji and message GIFs

**什么时候用 / When to Use**:
- 为Slack创建表情时 / Creating Slack emojis
- 添加动画反馈时 / Adding animated feedback
- 需要轻量GIF时 / Need lightweight GIFs
- Slack团队沟通时 / Slack team communication

**怎么用 / How to Use**:
```
告诉 Claude："为Slack创建一个GIF动画"
Tell Claude: "Create a GIF animation for Slack"

Claude 会使用 slack-gif-creator 技能
Claude will use slack-gif-creator skill
```

**举例 / Example**:
```
你说："创建一个'成功'的Slack表情"

技能会：
1️⃣ 设置128x128尺寸(emoji标准)
2️⃣ 设计动画帧
3️⃣ 优化颜色(减少文件大小)
4️⃣ 设置适当帧率(10-30 FPS)
5️⃣ 输出优化后的GIF

结果：完美适配Slack的动画表情!
```

### Purpose / 作用

Create animated GIFs optimized for Slack:
创建为 Slack 优化的动画 GIF：

- Proper dimensions
  - 适当的尺寸
- Optimized file size
  - 优化的文件大小
- Smooth animations
  - 流畅的动画

### Key Features / 主要特性

✨ **Slack Requirements / Slack 要求**
  - Emoji GIFs: 128x128
  - Message GIFs: 480x480
  - FPS: 10-30
  - Duration: Under 3 seconds

✨ **Optimization / 优化**
  - Color reduction
  - Frame optimization
  - Compression

### Dependencies / 依赖

```bash
pip install pillow imageio numpy
```

### Example / 示例

```python
from PIL import Image, ImageDraw
import numpy as np

def create_slack_gif():
    frames = []
    size = 128  # Emoji size

    for i in range(12):
        # Create frame
        img = Image.new('RGB', (size, size), (240, 248, 255))
        draw = ImageDraw.Draw(img)

        # Draw animated element
        offset = int(32 * (0.5 - 0.5 * (i % 2)))
        draw.ellipse([64+offset, 30, 64+offset+40, 70],
                     fill=(59, 130, 246))

        frames.append(img)

    # Save as GIF
    frames[0].save(
        'slack_emoji.gif',
        save_all=True,
        append_images=frames[1:],
        duration=100,  # 100ms per frame
        loop=0,  # Infinite loop
        optimize=True
    )

create_slack_gif()
```

### Animation Concepts / 动画概念

**Pulse/Heartbeat / 脉冲/心跳**
```python
scale = 0.8 + 0.2 * math.sin(i * 0.5)
```

**Bounce / 弹跳**
```python
t = i / (num_frames - 1)
y = 400 * (1 - math.sin(t * math.pi))
```

### Best Practices / 最佳实践

✅ Keep file size small / 保持文件大小小
✅ Use appropriate FPS / 使用适当的 FPS
✅ Test in Slack / 在 Slack 中测试

---

## 🎭 Theme Factory / 主题工厂

> __Quick Access / 快速访问:__ Use when applying themes / 应用主题时使用

### 💡 快速理解 / Quick Understanding

**是什么 / What**: 提供10个专业主题,可以让任何内容看起来专业一致
**Provides 10 professional themes that make anything look professional and consistent**

**能做什么 / Capabilities**:
- 应用专业配色 / Apply professional color schemes
- 统一视觉风格 / Unified visual style
- 快速主题切换 / Quick theme switching
- 适配不同内容 / Adapt to different content

**什么时候用 / When to Use**:
- 需要专业外观时 / Need professional appearance
- 保持品牌一致性时 / Maintaining brand consistency
- 快速美化内容时 / Quickly beautifying content
- 创建演示文档时 / Creating presentations

**怎么用 / How to Use**:
```
告诉 Claude："为这个内容应用主题"
Tell Claude: "Apply a theme to this content"

Claude 会使用 theme-factory 技能
Claude will use theme-factory skill
```

**举例 / Example**:
```
你有：一个普通的网页

技能会：
1️⃣ 选择合适主题(如Midnight Galaxy)
2️⃣ 应用配色方案
3️⃣ 统一字体和样式
4️⃣ 调整间距和布局
5️⃣ 确保可访问性

主题选择：
- Arctic Frost / 北极霜(清爽专业)
- Midnight Galaxy / 午夜银河(现代科技)
- Sunset Boulevard / 日落大道(温暖活力)

结果：瞬间变得专业美观!
```

### Purpose / 作用

Apply 10 professional themes to any content:
应用 10 个专业主题到任何内容：

- Arctic Frost / 北极霜
- Botanical Garden / 植物园
- Desert Rose / 沙漠玫瑰
- Forest Canopy / 森林树冠
- Golden Hour / 黄金时刻
- Midnight Galaxy / 午夜银河
- Modern Minimalist / 现代极简
- Ocean Depths / 海洋深处
- Sunset Boulevard / 日落大道
- Tech Innovation / 科技创新

### Key Features / 主要特性

✨ **Theme Components / 主题组件**
  - Color palettes
  - Typography
  - Styling patterns

✨ **Application / 应用**
  - HTML artifacts
  - Documents
  - Presentations

### Example / 示例

```css
/* Midnight Galaxy Theme */
:root {
  --primary-color: #1E3A8A;   /* Dark blue */
  --secondary-color: #4F46E5; /* Indigo */
  --accent-color: #8B5CF6;    /* Purple */
  --bg-color: #0F172A;        /* Dark slate */
  --text-color: #F1F5F9;      /* Light gray */
}

body {
  background-color: var(--bg-color);
  color: var(--text-color);
  font-family: 'Inter', sans-serif;
}

h1, h2, h3 {
  color: var(--primary-color);
}

.button {
  background-color: var(--accent-color);
  color: white;
}
```

### Theme Descriptions / 主题描述

| Theme / 主题 | Colors / 颜色 | Feel / 感觉 |
|-------------|--------------|-------------|
| Arctic Frost / 北极霜 | Cool blues, whites / 冷蓝色、白色 | Clean, crisp / 干净、清爽 |
| Botanical Garden / 植物园 | Greens, earth tones / 绿色、土色调 | Natural, organic / 自然、有机 |
| Desert Rose / 沙漠玫瑰 | Warm oranges, reds / 暖橙色、红色 | Bold, striking / 大胆、醒目 |
| Forest Canopy / 森林树冠 | Deep greens, browns / 深绿色、棕色 | Rustic, natural / 乡村、自然 |
| Golden Hour / 黄金时刻 | Warm yellows, ambers / 暖黄色、琥珀色 | Elegant, warm / 优雅、温暖 |
| Midnight Galaxy / 午夜银河 | Dark blues, purples / 深蓝色、紫色 | Modern, tech / 现代、科技 |
| Modern Minimalist / 现代极简 | Grays, black / 灰色、黑色 | Clean, simple / 干净、简单 |
| Ocean Depths / 海洋深处 | Deep blues, teals / 深蓝色、青色 | Professional / 专业 |
| Sunset Boulevard / 日落大道 | Vibrant oranges, pinks / 鲜艳的橙色、粉色 | Dramatic, bold / 戏剧性、大胆 |
| Tech Innovation / 科技创新 | Blues, cyans / 蓝色、青色 | Tech-focused / 专注于科技 |

### Best Practices / 最佳实践

✅ Use consistent theming / 使用一致的主题
✅ Consider accessibility / 考虑可访问性
✅ Test across different content / 在不同内容上测试

---

## 📊 Summary / 总结

### Visual Creation Workflow / 视觉创建工作流

```
Idea → Algorithmic Art → Canvas Design → Animated GIF → Themed Output
  ↓         ↓                  ↓              ↓              ↓
Concept  Generate          Refine         Animate         Apply
        Patterns          Details        Motion         Theme
```

### Key Principles / 关键原则

✨ **Creativity / 创造力**
  - Experiment freely
  - 自由实验
  - Learn from others
  - 向他人学习

✨ **Quality / 质量**
  - Optimize performance
  - 优化性能
  - Ensure smooth animations
  - 确保流畅的动画

✨ **Consistency / 一致性**
  - Use themes effectively
  - 有效使用主题
  - Maintain visual coherence
  - 保持视觉连贯性

---

## 🔗 Resources / 资源

- 📖 [Pillow Documentation](https://pillow.readthedocs.io/)
- 📖 [HTML5 Canvas Guide](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- 📖 [GIF Optimization Tips](https://ezgif.com/optimize)

---

_💡 Tip: Test animations on different devices for performance / 提示：在不同设备上测试动画以获得最佳性能_
