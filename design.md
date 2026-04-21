# Design System — Agent Crafted 入口页

> 参考风格：[Vercel](https://vercel.com) 官网设计语言

## 设计原则

1. **极简克制** — 大量留白，内容呼吸感强
2. **黑白为主** — 纯黑背景 + 纯白文字，点缀用渐变色
3. **几何秩序** — 网格对齐，圆角统一，间距一致
4. **微动效** — hover 时卡片微微上浮 + 边框渐变

## 配色方案

```
背景：     #000000（纯黑）
卡片：     #0a0a0a（近黑）
边框：     #1a1a1a（微亮分割线）
文字主色：  #ededed（近白）
文字副色：  #888888（灰色）
强调色：   蓝紫渐变 linear-gradient(135deg, #007CF0, #00DFD8)
hover边框：线性渐变动画
```

## 排版规范

```
标题字体：  -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif
代码字体：  'SFMono-Regular', Menlo, Consolas, monospace

主标题：    48px / font-weight: 800 / letter-spacing: -0.02em
副标题：    18px / font-weight: 400 / color: #888
卡片标题：  18px / font-weight: 600 / color: #ededed
卡片描述：  14px / font-weight: 400 / color: #888 / line-height: 1.6
标签：      12px / font-weight: 500 / 大写 / letter-spacing: 0.05em
```

## 卡片设计

```
尺寸：      最小宽度 280px，自适应网格 (auto-fill, minmax(300px, 1fr))
内边距：    24px
圆角：      12px
背景：      #0a0a0a
边框：      1px solid #1a1a1a
过渡：      transition: all 0.2s ease

hover 效果：
  - transform: translateY(-4px)
  - 边框变为渐变色（蓝紫渐变）
  - box-shadow: 0 8px 30px rgba(0, 124, 240, 0.1)
```

## 页面结构

```
┌─────────────────────────────────────────────┐
│  （大量留白）                                 │
│  AGENT CRAFTED                              │  ← 标题，大号加粗
│  Pages crafted by AI through conversations  │  ← 副标题，灰色
│  （留白）                                    │
├─────────────────────────────────────────────┤
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │ 🟢 网络   │  │ 🔵 DevOps│  │ 🟣 工具  │  │  ← 标签
│  │           │  │           │  │          │  │
│  │ Tailscale │  │ Docker    │  │ Git      │  │  ← 卡片标题
│  │ 完全速查   │  │ 速查手册   │  │ 速查手册 │  │  ← 描述
│  │ 手册       │  │ 手册       │  │         │  │
│  │           │  │           │  │          │  │
│  │ → 访问    │  │ → 访问    │  │ → 访问   │  │  ← 链接
│  └──────────┘  └──────────┘  └──────────┘  │
│                                             │
│  （大量留白）                                 │
├─────────────────────────────────────────────┤
│  Built with ♥ by AI agents                  │  ← 页脚
│  Powered by GitHub Pages                    │
└─────────────────────────────────────────────┘
```

## 动画细节

- 卡片进入：`fadeInUp`，stagger 延迟（每张卡片 +0.05s）
- Hover 上浮：`translateY(-4px)` + 边框渐变
- 页面加载：标题从上方淡入，副标题延迟 0.1s
- 渐变边框动画：`background-size: 200% 200%` + `animation: gradient-shift 3s ease infinite`

## 注意事项

- **不使用外部 CSS 框架**，纯内联样式
- **不使用外部字体 CDN**，系统字体栈
- **单文件 HTML**，自包含
- 暗色背景下的可访问性：文字对比度 ≥ 4.5:1
