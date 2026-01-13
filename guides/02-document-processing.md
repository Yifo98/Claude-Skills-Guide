# 📄 Document Processing Skills Guide / 文档处理技能指南

## 📄 文档处理技能指南

> __Official Sources / 官方来源:__
> Based on anthropics/skills repository
> 基于 anthropics/skills 仓库
>
> Please visit the official repository for the most up-to-date information.
> 请访问官方仓库获取最新信息。

---

## 📋 Overview / 概述

Document processing skills enable manipulation of common office formats including PDF, Word, PowerPoint, and Excel documents. These skills can extract content, create documents, and perform complex data transformations.

文档处理技能能够操作常见的办公格式，包括 PDF、Word、PowerPoint 和 Excel 文档。这些技能可以提取内容、创建文档和执行复杂的数据转换。

本指南涵盖了：
- **PDF Processing / PDF 处理** - Extract text, tables, images / 提取文本、表格、图像
- **Word Documents / Word 文档** - Read/write .docx files / 读写 .docx 文件
- **PowerPoint / PowerPoint** - Create presentations / 创建演示文稿
- **Excel Spreadsheets / Excel 电子表格** - Formulas, charts, data / 公式、图表、数据

---

## 📕 PDF / PDF 文档处理

> __Quick Access / 快速访问:__ Use when working with PDF files / 处理 PDF 文件时使用

### Purpose / 作用

Extract and analyze content from PDF documents:
从 PDF 文档提取和分析内容：

- Extract text with formatting
  - 提取带格式的文本
- Parse tables
  - 解析表格
- Extract images
  - 提取图像
- Handle encrypted PDFs
  - 处理加密 PDF

### Key Features / 主要特性

✨ **Text Extraction / 文本提取**
  - Preserve formatting
  - 保留格式
  - Handle multi-language
  - 处理多语言
  - Support OCR for scanned PDFs
  - 支持扫描 PDF 的 OCR

✨ **Table Extraction / 表格提取**
  - Parse complex tables
  - 解析复杂表格
  - Preserve structure
  - 保留结构
  - Export to CSV/Excel
  - 导出到 CSV/Excel

✨ **Image Extraction / 图像提取**
  - Extract all images
  - 提取所有图像
  - Save with metadata
  - 保存元数据
  - Support multiple formats
  - 支持多种格式

### Dependencies / 依赖

```bash
pip install pymupdf  # PyMuPDF
```

### Example / 示例

```python
import fitz  # PyMuPDF

# Extract text
doc = fitz.open("document.pdf")
for page in doc:
    text = page.get_text()
    print(text)

# Extract tables
for page in doc:
    tables = page.find_tables()
    for table in tables:
        df = table.to_pandas()
        print(df)

# Extract images
for page in doc:
    images = page.get_images()
    for img_index, img in enumerate(images):
        xref = img[0]
        pix = fitz.Pixmap(doc, xref)
        pix.save(f"image_{page.number}_{img_index}.png")
```

### Use Cases / 使用场景

- Extract data from reports
  - 从报告中提取数据
- Parse invoices and receipts
  - 解析发票和收据
- Analyze academic papers
  - 分析学术论文
- Convert PDF to text
  - 将 PDF 转换为文本

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Check if PDF is encrypted first
  - 首先检查 PDF 是否加密
  - Handle exceptions for corrupted PDFs
  - 处理损坏 PDF 的异常
  - Use OCR for scanned documents
  - 对扫描文档使用 OCR

❌ **DON'T / 避免做法**
  - Assume all PDFs have extractable text
  - 假设所有 PDF 都有可提取的文本
  - Ignore page layout
  - 忽略页面布局
  - Skip error handling
  - 跳过错误处理

---

## 📗 DOCX / Word 文档处理

> __Quick Access / 快速访问:__ Use when creating/editing Word documents / 创建/编辑 Word 文档时使用

### Purpose / 作用

Create and manipulate Microsoft Word documents:
创建和操作 Microsoft Word 文档：

- Create documents programmatically
  - 以编程方式创建文档
- Read existing documents
  - 读取现有文档
- Modify content and formatting
  - 修改内容和格式
- Add tables and images
  - 添加表格和图像

### Key Features / 主要特性

✨ **Document Creation / 文档创建**
  - Add headings and paragraphs
  - 添加标题和段落
  - Apply styles
  - 应用样式
  - Insert page breaks
  - 插入分页符

✨ **Content Manipulation / 内容操作**
  - Replace text
  - 替换文本
  - Add tables
  - 添加表格
  - Insert images
  - 插入图像
  - Add headers/footers
  - 添加页眉/页脚

✨ **Formatting / 格式化**
  - Bold, italic, underline
  - 粗体、斜体、下划线
  - Fonts and colors
  - 字体和颜色
  - Alignment and spacing
  - 对齐和间距

### Dependencies / 依赖

```bash
pip install python-docx
```

### Example / 示例

```python
from docx import Document
from docx.shared import Inches, Pt
from docx.enum.text import WD_ALIGN_PARAGRAPH

# Create new document
doc = Document()

# Add heading
doc.add_heading('Report Title', 0)

# Add paragraph with formatting
p = doc.add_paragraph()
p.add_run('Bold text').bold = True
p.add_run(' and ')
p.add_run('italic text').italic = True

# Add table
table = doc.add_table(rows=3, cols=3)
table.style = 'Table Grid'
for i in range(3):
    for j in range(3):
        table.cells[i][j].text = f'Cell {i},{j}'

# Add image
doc.add_picture('image.png', width=Inches(2.0))

# Save
doc.save('report.docx')

# Read existing document
doc = Document('existing.docx')
for para in doc.paragraphs:
    print(para.text)
```

### Use Cases / 使用场景

- Generate reports automatically
  - 自动生成报告
- Create invoices
  - 创建发票
- Fill templates
  - 填充模板
- Document mail merge
  - 文档邮件合并

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Use styles for consistency
  - 使用样式保持一致性
  - Save frequently during editing
  - 编辑时频繁保存
  - Test with Microsoft Word
  - 使用 Microsoft Word 测试

❌ **DON'T / 避免做法**
  - Hardcode all formatting
  - 硬编码所有格式
  - Forget to save changes
  - 忘记保存更改
  - Ignore compatibility
  - 忽略兼容性

---

## 📘 PPTX / PowerPoint 创建和编辑

> __Quick Access / 快速访问:__ Use when creating presentations / 创建演示文稿时使用

### Purpose / 作用

Create PowerPoint presentations programmatically:
以编程方式创建 PowerPoint 演示文稿：

- Create slides with various layouts
  - 创建不同布局的幻灯片
- Add text and shapes
  - 添加文本和形状
- Insert images and charts
  - 插入图像和图表
- Apply themes and templates
  - 应用主题和模板

### Key Features / 主要特性

✨ **Slide Creation / 幻灯片创建**
  - Multiple layout options
  - 多种布局选项
  - Title slides, content slides
  - 标题幻灯片、内容幻灯片
  - Custom layouts
  - 自定义布局

✨ **Content Addition / 内容添加**
  - Text boxes and placeholders
  - 文本框和占位符
  - Shapes and lines
  - 形状和线条
  - Images and media
  - 图像和媒体
  - Charts and graphs
  - 图表和图形

✨ **Styling / 样式**
  - Apply themes
  - 应用主题
  - Custom colors and fonts
  - 自定义颜色和字体
  - Animation and transitions
  - 动画和过渡

### Dependencies / 依赖

```bash
pip install python-pptx
```

### Example / 示例

```python
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.enum.text import PP_ALIGN

# Create presentation
prs = Presentation()

# Title slide
slide = prs.slides.add_slide(prs.slide_layouts[0])
title = slide.shapes.title
subtitle = slide.placeholders[1]
title.text = "Presentation Title"
subtitle.text = "Subtitle"

# Content slide with bullet points
slide = prs.slides.add_slide(prs.slide_layouts[1])
shapes = slide.shapes
title_shape = shapes.title
body_shape = shapes.placeholders[1]
title_shape.text = "Bullet Points"

tf = body_shape.text_frame
tf.text = "First bullet"
p = tf.add_paragraph()
p.text = "Second bullet"
p.level = 1

# Add image
slide = prs.slides.add_slide(prs.slide_layouts[5])
left = top = Inches(1)
pic = slide.shapes.add_picture('image.png', left, top)

# Save
prs.save('presentation.pptx')
```

### Use Cases / 使用场景

- Automated reporting
  - 自动报告
- Training materials
  - 培训材料
- Data visualization presentations
  - 数据可视化演示
- Template-based generation
  - 基于模板的生成

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Use slide layouts for consistency
  - 使用幻灯片布局保持一致性
  - Limit text per slide
  - 限制每张幻灯片的文本
  - Test in PowerPoint
  - 在 PowerPoint 中测试

❌ **DON'T / 避免做法**
  - Overcrowd slides
  - 幻灯片过度拥挤
  - Ignore aspect ratio
  - 忽略纵横比
  - Use too many animations
  - 使用过多动画

---

## 📙 XLSX / Excel 电子表格处理

> __Quick Access / 快速访问:__ Use when working with spreadsheets / 处理电子表格时使用

### Purpose / 作用

Manipulate Excel spreadsheets with formulas and charts:
使用公式和图表操作 Excel 电子表格：

- Read/write Excel files
  - 读写 Excel 文件
- Add formulas and functions
  - 添加公式和函数
- Create charts
  - 创建图表
- Apply formatting
  - 应用格式

### Key Features / 主要特性

✨ **Cell Operations / 单元格操作**
  - Read/write values
  - 读写值
  - Apply formatting
  - 应用格式
  - Add formulas
  - 添加公式
  - Merge cells
  - 合并单元格

✨ **Data Operations / 数据操作**
  - Insert/delete rows and columns
  - 插入/删除行和列
  - Sort and filter
  - 排序和筛选
  - Data validation
  - 数据验证

✨ **Charts / 图表**
  - Create various chart types
  - 创建各种图表类型
  - Customize appearance
  - 自定义外观
  - Add data labels
  - 添加数据标签

### Dependencies / 依赖

```bash
pip install openpyxl
```

### Example / 示例

```python
from openpyxl import Workbook, load_workbook
from openpyxl.styles import Font, PatternFill
from openpyxl.chart import BarChart, Reference

# Create new workbook
wb = Workbook()
ws = wb.active
ws.title = "Sales Data"

# Add headers
ws['A1'] = 'Product'
ws['B1'] = 'Quantity'
ws['C1'] = 'Price'
ws['D1'] = 'Total'

# Format headers
header_font = Font(bold=True, color="FFFFFF")
header_fill = PatternFill(start_color="366092", end_color="366092", fill_type="solid")
for cell in ws[1]:
    cell.font = header_font
    cell.fill = header_fill

# Add data
data = [
    ['Widget A', 10, 9.99],
    ['Widget B', 5, 14.99],
    ['Widget C', 8, 12.99],
]

for row_idx, row_data in enumerate(data, start=2):
    for col_idx, value in enumerate(row_data, start=1):
        cell = ws.cell(row=row_idx, column=col_idx, value=value)

# Add formula for total
for row in range(2, 5):
    ws[f'D{row}'] = f'=B{row}*C{row}'

# Create chart
chart = BarChart()
data = Reference(ws, min_col=4, min_row=1, max_row=5)
cats = Reference(ws, min_col=1, min_row=2, max_row=5)
chart.add_data(data, titles_from_data=True)
chart.set_categories(cats)
chart.title = "Sales Total"
ws.add_chart(chart, "F2")

# Save
wb.save('sales_report.xlsx')

# Read existing workbook
wb = load_workbook('existing.xlsx')
ws = wb.active

# Read cell values
for row in ws.iter_rows(min_row=1, max_row=10, values_only=True):
    print(row)
```

### Use Cases / 使用场景

- Financial reports
  - 财务报告
- Data analysis
  - 数据分析
- Invoice generation
  - 发票生成
- Data export/import
  - 数据导出/导入

### Best Practices / 最佳实践

✅ **DO / 推荐做法**
  - Use descriptive sheet names
  - 使用描述性的工作表名称
  - Add headers to data
  - 为数据添加标题
  - Format for readability
  - 为可读性格式化

❌ **DON'T / 避免做法**
  - Hardcode cell references
  - 硬编码单元格引用
  - Ignore data types
  - 忽略数据类型
  - Create overly complex formulas
  - 创建过于复杂的公式

---

## 📊 Summary / 总结

### Complete Document Workflow / 完整文档工作流

```
PDF Extract → Word Edit → Excel Analyze → PowerPoint Present
   ↓            ↓            ↓               ↓
Extract     Create      Calculate       Visualize
Content    Documents     Data          Information
```

### Common Use Cases / 常见使用场景

1. **Report Generation / 报告生成**
   - Extract data from PDFs
   - 从 PDF 提取数据
   - Analyze in Excel
   - 在 Excel 中分析
   - Present in PowerPoint
   - 在 PowerPoint 中展示

2. **Document Conversion / 文档转换**
   - PDF to Word
   - PDF to Excel
   - Word to PDF

3. **Automated Workflows / 自动化工作流**
   - Invoice processing
   - 发票处理
   - Report generation
   - 报告生成
   - Data migration
   - 数据迁移

### Key Principles / 关键原则

✨ **Preserve Formatting / 保留格式**
  - Maintain document structure
  - 维护文档结构
  - Keep styling consistent
  - 保持样式一致

✨ **Handle Errors / 处理错误**
  - Check for file existence
  - 检查文件是否存在
  - Handle corrupted files
  - 处理损坏的文件
  - Validate data
  - 验证数据

✨ **Optimize Performance / 优化性能**
  - Work with large files efficiently
  - 高效处理大文件
  - Use appropriate libraries
  - 使用适当的库

---

## 🔗 Resources / 资源

- 📖 [PyMuPDF Documentation](https://pymupdf.readthedocs.io/)
- 📖 [python-docx Documentation](https://python-docx.readthedocs.io/)
- 📖 [python-pptx Documentation](https://python-pptx.readthedocs.io/)
- 📖 [openpyxl Documentation](https://openpyxl.readthedocs.io/)

---

_💡 Tip: Combine document skills for complete automation workflows / 提示：组合文档技能以实现完整的自动化工作流_
