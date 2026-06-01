# Changelog

基于 [op7418/guizang-ppt-skill](https://github.com/op7418/guizang-ppt-skill) 的 fork 改版记录。

---

## 2026-06-01 · v2.0 — 新增两种风格 + 点击翻页

### 🆕 新增风格 C · 日式侘寂（Wabi-Sabi）

**模板**：`assets/template-wabi.html`
**主题**：`references/themes-wabi.md`

#### 视觉特征
- **和纸纹理背景**：SVG feTurbulence 生成的 fractalNoise 纹理，叠加在底色上模拟日本和纸质感
- **极细宋体**：Noto Serif SC 200/300 weight 为主标题字体，EB Garamond 意大利体做英文点缀
- **非对称布局**：内容区默认偏左 58%（`.wabi-left`），右侧留白或放图（`.wabi-right`），大量呼吸空间
- **墨渍装饰**：`.sumi-dot`（小圆点）、`.sumi-line`（极细横线）、`.sumi-stroke`（竖向渐隐线），模拟水墨渍痕
- **竖排侧边文字**：`.wabi-vertical` 使用 `writing-mode:vertical-rl`，日式竖排元素
- **和纸图片框**：`.washi-frame` 图片自动去饱和（`saturate(.85)`）+ 低对比度（`contrast(.92)`），叠加和纸纹理
- **慢速动效**：1.2s 淡入 + 12px 上移，像水墨晕开，stagger 150ms

#### 5 套主题色
| 主题 | ink | paper | 调性 |
|------|-----|-------|------|
| 🖋 暖墨（默认） | `#2c2c2c` | `#f7f5f0` | 暖深灰 + 暖米白 |
| 🌫️ 枯山水 | `#3a3a38` | `#f0efec` | 冷灰调，禅意 |
| 🔴 朱砂 | `#2e1f1a` | `#f5efe8` | 暖红棕，印泥感 |
| 🌿 青竹 | `#1e2a1e` | `#f4f2e8` | 竹绿 + 宣纸黄 |
| 🌙 月白 | `#1e2630` | `#f2f4f7` | 冷蓝白，月光感 |

#### 布局类
| 类名 | 作用 |
|------|------|
| `.wabi-left` | 左侧内容区（max-width:58%，padding-left:8vw） |
| `.wabi-right` | 右侧图片区（position:absolute，right:6vw） |
| `.wabi-center` | 居中布局（flex 居中 + text-align:center） |
| `.wabi-bottom` | 底部对齐（justify-content:flex-end） |
| `.wabi-grid-3` | 三列网格（适合对比/三要素页） |
| `.wabi-grid-2` | 两列网格 |

#### 字体类
| 类名 | 字体 | 用途 |
|------|------|------|
| `.kicker` | IBM Plex Mono | 极小标签（11px，大写） |
| `.wabi-title` | Noto Serif SC 200 | 大标题（min(6.2vw,10vh)） |
| `.wabi-title-md` | Noto Serif SC 300 | 中标题 |
| `.wabi-subtitle` | Noto Serif SC 300 | 副标题 |
| `.wabi-lead` | Noto Serif SC 300 | 引语/lead |
| `.wabi-body` | Noto Sans SC 400 | 正文 |
| `.wabi-en` | EB Garamond italic | 英文点缀 |
| `.wabi-meta` | IBM Plex Mono | 底部元数据 |
| `.wabi-num` | EB Garamond 400 | 装饰性大数字 |

---

### 🆕 新增风格 D · 新丑主义（Brutalism）

**模板**：`assets/template-brutal.html`
**主题**：`references/themes-brutal.md`

#### 视觉特征
- **超粗无衬线**：Inter 900 weight，全大写英文标题，字号 min(12vw,18vh)
- **3px 粗描边卡片**：`.brutal-card` 使用 `border:3px solid`，可叠加 `.accent-red` / `.accent-yellow` / `.accent-blue` 变色
- **贴纸标签**：`.sticker` 组件带 `transform:rotate(-2deg)`，背景默认黄色，`.red` / `.blue` 变体
- **装饰色块**：`.brutal-block` 绝对定位色块，故意溢出页面边界，可选 `.red` / `.yellow` / `.blue` / `.fg`
- **快速弹性动效**：0.4s 淡入 + 20px 上移，stagger 60ms，干脆利落
- **深色 slide**：`.slide.dark` 用前景色做背景，`.slide.accent-red` / `.accent-yellow` 全色块背景

#### 4 套主题色
| 主题 | bg | fg | accent 色 | 调性 |
|------|----|----|----------|------|
| ⚡ 经典（默认） | `#fff` | `#000` | 红/黄/蓝三原色 | David Carson 反叛 |
| ⚫ 单色 | `#fff` | `#000` | 纯灰阶 | Xerox 复印机感 |
| 🎨 莫兰迪 | `#f5f0eb` | `#3d3632` | 低饱和粉彩 | 温柔新丑 |
| 🔥 热力 | `#0a0a0a` | `#f0f0f0` | 红→橙→琥珀 | 暗黑热烈 |

#### 布局类
| 类名 | 作用 |
|------|------|
| `.brutal-split` | 两列网格（1fr 1fr） |
| `.brutal-grid-3` | 三列网格 |
| `.brutal-center` | 居中布局 |
| `.brutal-bottom` | 底部对齐 |
| `.brutal-col` | 纵向 flex + gap:2vh |

#### 组件类
| 类名 | 作用 |
|------|------|
| `.brutal-card` | 3px 粗描边卡片 |
| `.brutal-card.accent-red` | 红底白字卡片 |
| `.brutal-card.accent-yellow` | 黄底黑字卡片 |
| `.brutal-card.accent-blue` | 蓝底白字卡片 |
| `.brutal-card.dark` | 黑底白字卡片 |
| `.sticker` | 黄底贴纸标签（旋转 -2°） |
| `.sticker.red` | 红底贴纸（旋转 -1°） |
| `.sticker.blue` | 蓝底贴纸（旋转 1°） |
| `.brutal-block` | 绝对定位装饰色块 |

---

### ✏️ 点击翻页功能（全风格适用）

**改动文件**：`template.html`、`template-swiss.html`、`template-wabi.html`、`template-brutal.html`

#### 功能说明
- 点击页面**左 1/3 区域** → 上一页
- 点击页面**右 2/3 区域** → 下一页
- 自动排除交互元素（按钮、链接、输入框、导航栏、ESC 索引面板）
- 与现有键盘、滚轮、触屏翻页完全兼容

#### 代码位置
每个模板的导航 JS 区域新增：
```javascript
/* 点击翻页 */
deck.addEventListener('click', e => {
  if (e.target.closest('button, a, input, select, textarea, #nav, #overview')) return;
  const x = e.clientX / window.innerWidth;
  go(x < 1/3 ? idx - 1 : idx + 1);
});
```

#### 提示文字更新
- 原：`← → 翻页 · B 静态 · ESC 索引`
- 新：`点击翻页 · ← → · B 静态 · ESC 索引`

---

### 📝 SKILL.md 更新

- 更新了 frontmatter description，描述从"两种风格"改为"四种风格"
- 新增风格 C、D 的完整描述（视觉特征、适用场景、模板路径）
- 更新了风格选择参考表（问题 1），新增侘寂风和新丑风的匹配关键词
- 更新了 Step 2 拷贝模板的代码示例，新增两个 `cp` 命令
- 更新了资源文件导览，新增 `template-wabi.html`、`template-brutal.html`、`themes-wabi.md`、`themes-brutal.md`
- 新增了风格 C、D 的设计原则（各 7-8 条）
- 新增了风格 C、D 的参考作品来源

---

### 📊 数据汇总

| 项目 | 原版 | 改版后 |
|------|------|--------|
| 风格数量 | 2 种 | **4 种** |
| 主题数量 | 9 套 | **18 套** |
| 模板文件 | 2 个 | **4 个** |
| 主题文档 | 2 个 | **4 个** |
| 翻页方式 | 5 种 | **6 种**（+点击翻页） |
| 总代码量 | ~1700 行 | ~2600 行 |
