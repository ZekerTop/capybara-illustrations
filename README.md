# Capybara Illustrations Skill

中文 | [English](./README.en.md)

这是一个适合放在 Codex 里的创作辅助 skill：把观点、文章、社媒内容、开源项目说明、产品状态和教程内容，转成有**松弛感、情绪稳定感和一点幽默感**的卡皮巴拉（水豚）插图。

```text
Display name: Capybara Illustrations
Skill ID: capybara-illustrations
Usage: Use $capybara-illustrations ...
```

它不是火柴人 skill 的换皮版本，而是一个独立的角色型视觉系统。默认主体是卡皮巴拉：圆润、慢悠悠、随遇而安、看起来很稳，有一点萌，但不幼稚。它适合表达“把混乱放慢一点”“事情没有那么糟”“先做下一步”“温和但可靠”这类创作者内容。

仓库名使用 `capybara-illustrations`，保持简洁和可搜索；`vibe` 不放进仓库名，但已经写进默认风格规则里。

## 默认视觉语言

用户调用时不需要重复写基础要求。只要给出观点、文章、场景或想表达的意思，skill 会自动套用这些默认值：

- 主体是卡皮巴拉（水豚），不是火柴人、仓鼠、熊或固定吉祥物
- 默认 `16:9` 画幅，除非用户指定其他尺寸
- 白底或透明白底
- 黑色线稿
- 默认使用柔和暖棕色主体和一个克制点缀色
- 用户说 `mono`、`黑白`、`不要颜色` 时切换为纯黑白线稿
- 用户说 `soft-color`、`有点颜色` 时使用轻量彩色版
- 表情稳定、松弛、慢半拍，但动作要能表达观点
- 默认加入短标题、状态词、物件标签或一句 punchline
- 每张图只表达一个核心意思
- 不模仿任何具体创作者、品牌、IP、插画师或公开示例风格

文字不是越少越好。默认会给关键物件、状态和动作加短标注，让读者不用猜画面含义。只有用户明确说“无文字”“不要标注”或“纯图”时，才生成无文字版。

## 适合做什么

这个 skill 适合把抽象内容变成一张有情绪的卡皮巴拉场景图：

| 场景 | 适合输出 | 默认画幅 |
|---|---|---|
| 观点图 | 一句话观点、金句、认知转折 | `16:9` |
| 文章 / Newsletter | 正文解释图、章节停顿图、开头钩子图 | `16:9` / `3:2` |
| 社媒轮播 | 5-8 页连续概念图，每页一个动作 | `4:5` / `1:1` |
| SaaS 状态 | 空状态、错误页、加载页、成功页 | `1:1` / `3:2` / transparent spot |
| 开源 README | 安装、配置、issue、PR、release 流程 | `16:9` / `2:1` |
| PPT / Keynote | 章节过渡、观点旁图、轻量隐喻图 | `16:9` |
| 教程 / 课程 | 步骤图、练习图、反馈循环图 | `16:9` / `4:3` |

## 不适合做什么

不要用它来生成：

- 写实动物照片
- 复杂商业插画、3D、拟物或重度渲染图
- 固定品牌吉祥物、表情包角色或儿童贴纸
- 正式流程图模板、复杂架构图、密集 PPT 信息图
- 模仿某个插画师、创作者、品牌或现成示例的图
- 需要大量文字排版的海报终稿

如果你需要的是“正式商业 KV”，这个 skill 更适合作为前期概念草图和轻量插图方向。

## 安装

### 推荐方式：直接让 Codex 安装

在 Codex 里新开一个对话，把这个 GitHub 链接发给 Codex，然后让它帮你安装：

```text
请帮我安装这个 Codex skill：
https://github.com/ZekerTop/capybara-illustrations
```

Codex 会读取这个仓库里的 skill 文件，并把它安装到本地 skills 目录。安装完成后，按 Codex 的提示刷新或重启 Codex。

如果你 fork 了仓库，把链接换成自己的 GitHub 仓库地址即可。

### 本地源码安装

把 skill 文件夹复制到 Codex skills 目录：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./capybara-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

然后重启 Codex。

## 最快开始

生成一张观点图：

```text
Use $capybara-illustrations 为这个观点生成一张图：

“好的工具会把混乱收起来，把下一步摆到你面前。”
```

用户不需要再写“16:9、白底黑线、卡皮巴拉主体、文字说明、颜色”等基础要求。

使用黑白线稿版：

```text
Use $capybara-illustrations 用 mono 模式为这个观点生成一张图：

“不是所有事情都要立刻解决，有些事情先放进盒子里。”
```

为文章规划插图，先不要生图：

```text
Use $capybara-illustrations 阅读下面文章，先不要生图。

<粘贴文章>
```

为 SaaS 空状态生成插图：

```text
Use $capybara-illustrations 用 saas-state preset 生成空状态插图：

状态：用户还没有创建任何项目。
```

把主题设计成社媒轮播：

```text
Use $capybara-illustrations 用 carousel preset 把这个主题设计成社媒轮播，先不要生图。

主题：一个人如何把 AI 变成日常工作流
```

## Presets

| Preset | 用途 | 默认数量 | 画幅 | 重点 |
|---|---|---:|---|---|
| `idea` | 单张观点图 | 1 | `16:9` | 一句话观点变成卡皮巴拉动作场景 |
| `article` | 博客、文章、长文笔记 | 3-6 | 默认 `16:9` | 关键认知转折，不平均配图 |
| `newsletter` | 邮件、周报、精选摘要 | 1-3 | 默认 `16:9` | 轻量节奏和情绪缓冲 |
| `carousel` | 社媒轮播 | 5-8 | `4:5` / `1:1` | 一页一个动作或反差 |
| `saas-state` | 空状态、错误、权限、加载、成功 | 1 | `1:1` / `3:2` / transparent spot | 清楚标注状态和下一步 |
| `readme` | 开源 README、贡献指南、release notes | 2-4 | 默认 `16:9` | 工程文档里的温和解释图 |
| `slides` | PPT、Keynote、演讲 | 3-8 | `16:9` | 观点旁图，不抢层级 |
| `course` | 教程、课程、讲义 | 4-10 | `16:9` / `4:3` | 学习动作和反馈循环 |

## 工作流

### 1. 读内容，找视觉锚点

skill 会先从内容中挑出适合视觉化的部分，例如：

- 核心判断
- 混乱到秩序的变化
- 读者容易卡住的地方
- 情绪从焦虑到稳定的转折
- 步骤转换
- 输入输出
- 下一步行动

不适合被画出来的段落会被跳过。

### 2. 默认先出 shot list

除非用户明确说“直接生成 / 现在生图 / 不要规划”，否则先输出 shot list。每张图会说明：

- 放置位置或使用渠道
- 画幅
- 主题
- 核心意思
- 构图模式
- 卡皮巴拉动作
- 情绪
- 主要元素
- 建议标注
- 优先级

每次输出 shot list 后，都应该给出“下一步”提示，让用户知道可以直接回复什么：

```text
下一步：
- 回复“生成 #1”
- 回复“生成 #1 和 #2”
- 回复“调整 #1：改成 mono，不要标题”
- 回复“先不生成，重新检查插图位置”
```

### 3. 生成单张图

生成时，skill 会自动处理：

- 卡皮巴拉主体
- 画幅
- 背景
- 黑色线稿
- 彩色或黑白模式
- 表情和姿态
- 短标题、状态词、物件标签或 punchline
- 避免第三方 IP 和风格模仿

每张图单独生成，不默认把多张图拼成一张。

## 目录结构

```text
capybara-illustrations/
├── README.md
├── README.en.md
├── examples/
│   ├── prompts.md
│   └── prompts.en.md
└── capybara-illustrations/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── visual-system.md
        ├── presets.md
        ├── prompt-template.md
        ├── scene-patterns.md
        └── qa-checklist.md
```

## 关系说明

`capybara-illustrations` 和 `stick-figure-illustrations` 是两个独立 skill：

- `stick-figure-illustrations`：匿名火柴人，适合中性解释图和轻量流程图。
- `capybara-illustrations`：卡皮巴拉（水豚）角色，适合松弛感、情绪稳定感和更有趣的观点表达。

两个仓库分开维护，避免一个 skill 同时承担两套主体和气质。
