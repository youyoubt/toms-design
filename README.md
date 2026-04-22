# TOMS Operator Design System

Enterprise SaaS design system for payment terminal management consoles — built with Vue 3 + Element Plus + Poppins. Light-mode-first, data-dense, CJK-ready.

## Files

| File | Description |
|------|-------------|
| [DESIGN.md](./DESIGN.md) | Full design spec — colors, typography, components, layout, elevation |
| [preview.html](./preview.html) | Visual LivePreview — all tokens and components rendered |

---

## Use with AI

Provide both links as context when prompting AI tools:

- **DESIGN.md**: `https://github.com/youyoubt/toms-design/blob/main/DESIGN.md`
- **Preview**: `https://github.com/youyoubt/toms-design/blob/main/DESIGN.md`

---

## Prompt Templates

### System Prompt
> Paste into Claude Projects / Cursor Rules / Copilot Instructions — set once, use forever.

```
You are a frontend engineer for the TOMS Operator platform — an enterprise terminal management SaaS built with Vue 3 + Element Plus + Tailwind CSS.

Design System:
- DESIGN.md: https://raw.githubusercontent.com/youyoubt/toms-design/main/DESIGN.md
- Visual preview: https://youyoubt.github.io/toms-design/preview.html

Rules (non-negotiable):
1. Font: Poppins with CJK fallback ('PingFang SC', 'Microsoft YaHei')
2. App background: #f1f3f6 · Surface (cards/dialogs): #ffffff
3. Primary action color: #409eff · Brand anchor: #003a8c (step indicators, active nav only)
4. Primary text: #303133 · Data/table text: 14px weight 400
5. Card shadow: 0px 2px 4px -2px rgba(0,0,0,0.12), 0px 4px 8px 0px rgba(0,0,0,0.08), 0px 4px 16px 4px rgba(0,0,0,0.04)
6. Status colors — semantic only: Active #52c41a · Inactive #ff8d1a · Error #e9378f · Disabled #a6a6a6
7. Table cells: padding 5px 10px · border 1px solid #dcdfe6 · row hover rgba(9,30,66,0.04)
8. Page layout: 60px navbar (#ffffff) + 250px sidebar (#ffffff) + content area (#f1f3f6, 20px padding)
9. Buttons: primary #409eff 8px 20px r:4px · default #fff + #dcdfe6 border · text buttons for table actions
10. All UI must support i18n string length variance (EN / ZH / JA / FR / PT)
```

---

### New Page
> Use when building a module page from scratch.

```
参考 TOMS Operator 设计规范（DESIGN.md + preview.html），帮我实现 [页面名称] 页面。

技术栈：Vue 3 + Element Plus + Tailwind CSS
设计规范：https://raw.githubusercontent.com/youyoubt/toms-design/main/DESIGN.md

页面结构：
- 顶部：页面标题（24px Poppins 600 #303133）+ 右侧主操作按钮（#409eff）
- 筛选栏：若干 Select（width:200px）+ 搜索 Input + Search 按钮（compact: 3px 13px）
- 数据表格：14px，cell padding 5px 10px，表头 #f5f5f5，行 hover rgba(9,30,66,0.04)
  - 状态列：pill 徽标（Active #52c41a / Inactive #ff8d1a / Error #e9378f，12px 500 2px 8px r:3px）
  - 操作列：text button，右对齐
- 底部：分页（右对齐，active page #409eff，16px top margin）

具体业务需求：
[描述页面内容，如：终端列表，字段包括 TID / 型号 / 商户 / 状态 / 最后在线时间]
```

---

### Single Component
> Use when you need one specific component.

```
使用 TOMS Operator 设计系统（Element Plus + Poppins），生成 [组件名称] 组件。

设计 token：
- 背景 #ffffff · 边框 1px solid #dcdfe6 · radius 4px
- 主色 #409eff · 文字 #303133 · 次级文字 #767676
- 状态 pill：Active #52c41a / Inactive #ff8d1a / Error #e9378f，均为 12px/500/2px 8px/r:3px
- 卡片阴影：0px 2px 4px -2px rgba(0,0,0,.12), 0px 4px 8px rgba(0,0,0,.08), 0px 4px 16px 4px rgba(0,0,0,.04)

组件需求：
[描述该组件的功能、字段、交互行为]
```

---

### Dashboard / KPI Widgets

```
参考 TOMS Operator 设计规范，帮我实现仪表盘 KPI 卡片区域。

统计卡样式：
- 背景 #ffffff · border-radius 8px · 标准三层卡片阴影
- 大数字：32px Poppins 700 · 颜色跟随状态（正常 #12263f / 在线 #52c41a / 离线 #ff8d1a / 异常 #e9378f）
- 标签：16px 400 #677796 · line-height 17px
- 趋势标注：12px 500，正向 #52c41a / 负向 #e9378f
- 布局：flex 等宽排列，gap 12px

需要展示的指标：
[如：总终端数 / 在线数 / 离线数 / 故障数]
```

---

### Form / Configuration Page

```
参考 TOMS Operator 设计规范，帮我实现 [功能名称] 配置表单。

表单规范：
- 包裹在 #ffffff 卡片中（20px padding，8px radius，标准卡片阴影）
- Label：14px Poppins 400 #606266，display block，margin-bottom 6px
- Input：border 1px solid #dcdfe6，radius 4px，focus border #409eff，width 200px（行内）/ 100%（堆叠）
- Select：同 Input 样式，appearance none，自定义下拉箭头
- 表单项间距：margin-bottom 15px
- 底部操作：右对齐，Cancel（默认按钮）+ Submit（#409eff 主按钮）

表单字段：
[列出字段名称、类型、是否必填、校验规则]
```

---

### Quick Color Cheatsheet
> Copy into any prompt for instant color context.

```
TOMS Design Tokens:
App BG:#f1f3f6 | Surface:#ffffff | Brand:#003a8c | Primary:#409eff | Hover:#2c7be5
Text:#303133 | Nav:#6e84a3 | Active Nav:#12263f | Secondary:#767676 | Label:#677796
Active:#52c41a | Inactive:#ff8d1a | Danger:#e9378f | Warning:#f6c556 | Disabled:#a6a6a6
Border:#dcdfe6 | Card Border:#dae0e8 | Divider:#eef0f7 | Row Hover:rgba(9,30,66,0.04)
Shadow: 0px 2px 4px -2px rgba(0,0,0,.12),0px 4px 8px rgba(0,0,0,.08),0px 4px 16px 4px rgba(0,0,0,.04)
Font: 'Poppins','PingFang SC','Microsoft YaHei',Arial,sans-serif
```
