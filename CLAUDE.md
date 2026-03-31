# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

个人简历静态网站项目，使用纯 HTML/CSS/JavaScript 构建，无框架依赖。

## Commands

```bash
# 本地预览 - 直接用浏览器打开
open index.html

# 部署 - 推送到 GitHub Pages 或任意静态托管
git push origin main
```

## Architecture

```
uzong/
├── index.html      # 单页面应用，包含所有内容模块
├── css/style.css   # 响应式样式，CSS变量定义主题色
└── js/main.js      # 交互逻辑：导航、滚动动画、表单处理
```

**页面模块**（index.html 中的 section）：
- Hero（首页）→ About（关于）→ Skills（技能）→ Experience（经历）→ Projects（项目）→ Contact（联系）

**样式系统**（css/style.css）：
- CSS 变量在 `:root` 中定义，修改 `--primary-color` 可快速更换主题色
- 响应式断点：768px（移动端导航）、480px（小屏幕）

**交互功能**（js/main.js）：
- 移动端汉堡菜单切换
- 滚动时导航高亮当前 section
- 技能条进入视口时的动画
- 表单提交处理（当前为 alert 提示，可对接后端 API）

## Coding Standards

### HTML
- 使用语义化标签（`<nav>`, `<section>`, `<footer>`）
- 中文页面，`lang="zh-CN"`
- 图标使用 Font Awesome，保持统一的图标风格
- 表单元素必须有 `label` 或 `placeholder`

### CSS
- 使用 CSS 变量管理主题色，定义在 `:root` 中
- 命名规范：BEM 风格（`.block__element--modifier`）或语义化类名
- 响应式优先，移动端断点 768px
- 避免硬编码颜色值，使用 `var(--primary-color)` 等
- 动画使用 `transition` 而非 `animation`，保持简洁

### JavaScript
- 使用 ES6+ 语法（`const/let`、箭头函数、模板字符串）
- 事件委托优先，减少事件绑定数量
- DOM 操作前检查元素是否存在
- 使用 `IntersectionObserver` 处理滚动相关动画
- 表单验证使用原生 HTML5 验证 + JS 增强

### Git Commit
- 提交信息使用中文或英文，保持一致
- 格式：`<type>: <description>`（feat/fix/docs/style/refactor）
- 每次提交保持原子性，一个功能点一次提交
