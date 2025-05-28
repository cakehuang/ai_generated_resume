# AI 简历生成应用 - iPhone 原型

本项目是 AI 简历生成应用的原型设计，通过 iPhone 设备模拟框架展示应用界面，提供更真实的移动设备浏览体验。

## 使用方法

1. 打开 `index.html` 文件查看完整的原型展示
2. 点击页面顶部的导航按钮切换不同的页面视图
3. 所有页面将在 iPhone 设备模拟框架中展示

## 目录结构

- `common/` - 公共资源目录
  - `images/` - 图片资源目录（包含 iPhone 模拟所需的 SVG 图标）
  - `iphone-mockup.css` - iPhone 设备模拟样式
  - `styles.css` - 应用通用样式
  - `tabbar.html` - 底部标签栏组件
- `resume/` - 简历相关页面
- `service/` - 服务相关页面
- `profile/` - 个人中心相关页面
- `login.html` - 登录页面
- `home.html` - 首页
- `index.html` - 主入口页面（带 iPhone 设备模拟框架）

## 技术实现

- 使用纯 HTML、CSS 实现
- 样式基于 Tailwind CSS
- 使用 iframe 在 iPhone 模拟框架中加载各页面
- SVG 图标用于模拟 iPhone 状态栏

## 设计规范

详见 `/docs/pr.md` 文件中的设计规范。
