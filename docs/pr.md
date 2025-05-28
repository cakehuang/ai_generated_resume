# AI 简历生成应用 - 原型设计规范

## 1. 设计概述

### 1.1 设计理念

本应用的设计理念是"简约而不简单"，通过直观且现代化的界面，帮助用户轻松创建和管理专业简历。我们追求清晰的视觉层次、流畅的用户体验和高效的功能操作。

### 1.2 设计目标

- 降低用户创建高质量简历的门槛
- 简化复杂的简历编辑流程
- 提供直观的 AI 简历优化体验
- 确保全应用的一致性和连贯性

## 2. 设计规范

### 2.1 色彩系统

使用 Tailwind CSS 默认色彩系统：

#### 主色调

- 主色：purple-600（Tailwind 默认的主题色）
- 辅助色：emerald-500（绿色）
- 强调色：amber-500（橙黄色）

#### 中性色

- 背景色：gray-50
- 卡片背景：white
- 分割线：gray-200

#### 文本色

- 主要文本：gray-900
- 次要文本：gray-600
- 提示文本：gray-400
- 链接文本：purple-600

#### 功能色

- 成功：emerald-500
- 警告：amber-500
- 错误：red-500
- 信息：sky-500

### 2.2 排版

#### 字体

使用 Tailwind 默认字体系统：

- font-sans 类（系统默认无衬线字体）

#### 字号

使用 Tailwind 的文本大小类：

- 大标题：text-xl (20px)
- 中标题：text-lg (18px)
- 小标题：text-base (16px)
- 正文：text-sm (14px)
- 辅助文本：text-xs (12px)

#### 行高

- 标题：leading-snug
- 正文：leading-normal

### 2.3 布局规范

#### 间距

使用 Tailwind 的间距类：

- p-1, m-1 (4px)
- p-2, m-2 (8px)
- p-3, m-3 (12px)
- p-4, m-4 (16px)
- p-6, m-6 (24px)

#### 尺寸

- 页面宽度：w-full
- 内容最大宽度：max-w-md（约为 448px，接近 iPhone 15 的 390px）
- 导航栏高度：h-14 (56px)
- 底部标签栏高度：h-16 (64px)

### 2.4 组件设计

#### 按钮

- 主要按钮：bg-purple-600 text-white
- 次要按钮：bg-white text-purple-600 border border-purple-600
- 文本按钮：text-purple-600
- 按钮高度：h-11
- 按钮圆角：rounded-md

#### 输入框

- 高度：h-11
- 圆角：rounded-md
- 边框颜色：border border-gray-200
- 聚焦边框：focus:border-purple-600 focus:ring-1 focus:ring-purple-600
- 内边距：px-3 py-2.5

#### 卡片

- 背景色：bg-white
- 圆角：rounded-xl
- 阴影：shadow
- 内边距：p-4

#### 列表项

- 高度：min-h-14
- 分割线颜色：border-gray-200
- 内边距：px-4 py-3

#### 图标

- 导航图标：w-6 h-6
- 功能图标：w-5 h-5
- 指示图标：w-4 h-4

### 2.5 交互规范

#### 反馈

- 点击按钮：transform scale-95 opacity-90
- 表单提交：使用加载动画组件
- 操作成功：成功提示，持续 2 秒
- 操作失败：错误提示，可关闭

#### 转场动画

可以使用 Tailwind 的过渡类：

- 页面切换：transition-transform duration-300
- 弹窗显示：transition-all duration-200 transform
- 列表加载：transition-opacity delay-[index*50ms]

## 3. 页面结构

### 3.1 整体架构

- 底部标签栏导航
  - 首页
  - 简历
  - 服务
  - 我的

### 3.2 核心页面列表

1. 登录/注册页
2. 首页
3. 简历列表页
4. 简历详情页
5. 简历编辑相关页面
6. 服务列表与详情页
7. 支付流程页面
8. 个人中心页

### 3.3 交互流程

1. 用户登录 → 进入首页
2. 首页 → 创建简历 → 编辑个人信息 → 填写求职意向 → 选择 AI 优化服务
3. 服务购买 → 支付 → 获得优化结果
4. 简历导出与管理

## 4. 原型实现说明

### 4.1 技术选择

- **HTML5 + Tailwind CSS**（必须使用 Tailwind CSS 实现界面样式）
- 响应式设计，优先移动端体验
- 使用 iframe 实现多页面展示

### 4.2 文件结构

- 所有原型文件必须输出在根目录下的 `pr` 文件夹中
- `pr/index.html` - 入口页面，包含所有页面的 iframe 展示
- `pr/login.html` - 登录页面
- `pr/home.html` - 首页
- `pr/resume/` - 简历相关页面
- `pr/service/` - 服务相关页面
- `pr/profile/` - 个人中心页面
- `pr/common/` - 公共组件和样式

### 4.3 Tailwind CSS 实现指南

#### 4.3.1 Tailwind CSS 引入方式

在每个 HTML 文件的 `<head>` 中添加以下 CDN 链接：

```html
<link
  href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css"
  rel="stylesheet"
/>
```

#### 4.3.2 示例代码

使用 Tailwind 实现按钮的示例：

```html
<!-- 主要按钮 -->
<button
  class="bg-purple-600 text-white py-2 px-6 rounded-md h-11 font-medium hover:bg-purple-700 transition"
>
  按钮文本
</button>

<!-- 次要按钮 -->
<button
  class="bg-white text-purple-600 py-2 px-6 rounded-md h-11 font-medium border border-purple-600 hover:bg-purple-50 transition"
>
  按钮文本
</button>
```

使用 Tailwind 实现卡片的示例：

```html
<div class="bg-white rounded-xl shadow p-4 mb-4">
  <h3 class="text-base font-medium text-gray-900 mb-2">卡片标题</h3>
  <p class="text-gray-600 text-sm">卡片内容</p>
</div>
```

### 4.4 设计实现要点

- 所有页面保持统一的视觉风格
- 确保界面简洁明了，减少视觉噪音
- 重点突出关键功能和内容
- 表单设计注重易用性和清晰性
- 使用适当的空白和分组提高可读性
- 尽量用开源的图标和图片
- **必须使用 Tailwind CSS 的工具类来实现界面样式**

## 5. 改进与迭代计划

- 基于用户测试反馈持续优化界面
- 未来版本考虑增加更多个性化定制选项
- 提高 AI 生成内容的可视化展示
- 探索更多互动式编辑体验
