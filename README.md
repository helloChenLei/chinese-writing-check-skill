# chinese-writing-check

AI Agent Skill：中文写作规范校验工具。

给 AI 一篇文章，它会按照 28 条规则逐项扫描，输出结构化的校验报告——哪里有错、为什么错、怎么改。

## 它检查什么？

七大类、28 条规则，覆盖排版、用词和文风三个层面：

| 类别 | 检查内容 | 示例 |
|------|----------|------|
| **标点符号** | 全角/半角、直角引号、破折号、省略号、标点不重复 | `——` 而非 `---` |
| **中英文混排** | 空格、专有名词大小写、缩写、产品名 | `GitHub` 而非 `Github` |
| **数字用法** | 一位数汉字、两位以上阿拉伯、数字前后空格 | `共 12 人` 而非 `共12人` |
| **用词规范** | 禁用词、慎用词、陈词滥调、网络热词、专有名词查证 | 避免「高大上」「给力」 |
| **避免欧化中文** | 多余量词/代词、抽象名词泛滥、中英夹杂、音译 | `这非常不负责任` 而非 `这是一种非常不负责任的行为` |
| **文风检查** | 新闻联播体、淘宝体、自嗨型、说人话 | 清晰比聪明更好 |
| **翻译/双语** | 中英语义对应、英文语法检查 | 翻译后二次检查语义 |

## 安装

### 方式一：Cursor IDE

```bash
# 克隆到 Cursor 的个人 Skills 目录
git clone https://github.com/helloChenLei/chinese-writing-check.git ~/.cursor/skills/chinese-writing-check
```

安装后，在 Cursor 中对 AI 说「帮我检查这篇文章」即可触发。

### 方式二：Claude Code

```bash
# 克隆到 Claude Code 的 Skills 目录
git clone https://github.com/helloChenLei/chinese-writing-check.git ~/.claude/skills/chinese-writing-check
```

### 方式三：手动安装

1. 下载本仓库的 `SKILL.md` 和 `standards.md` 两个文件
2. 放到你的 AI 工具对应的 Skills 目录下即可

## 使用方式

安装后，在对话中说以下任意一种触发词：

- 「帮我检查这篇文章」
- 「校验写作」
- 「文字规范检查」
- 「校对」

然后提供文章内容（直接粘贴文本、给文件路径、或给 URL），AI 会输出结构化校验报告：

```
📝 中文写作规范校验报告

总评
- 检查条数：28
- 发现问题：5 处
- 严重程度分布：🔴 3 / 🟡 1 / 🟢 1

🔴 中英文混排 — 问题 3 处
...

✅ 总结与建议
...
```

严重程度含义：
- 🔴 **错误**：标点错误、禁用词、专有名词大小写错误、空格缺失
- 🟡 **建议**：欧化表达、慎用词、陈词滥调、文风问题
- 🟢 **优化**：可进一步精简、更自然的表达方式

## 文件结构

```
chinese-writing-check/
├── SKILL.md        # 主入口：校验流程 + 检查清单（给 AI 读的）
├── standards.md    # 详细规范：所有规则的正误对照表（给 AI 和人读的）
└── README.md       # 本文件
```

## 规范来源

本 Skill 的规则综合整理自以下四篇文章：

- [汉洋《写作入门》](https://hanyang.wtf/p/c7a) — 标点、禁用词、数字、文风
- [汉洋《给人文工作者的 AI 使用指南》](https://hanyang.wtf/p/ai) — 写作原则与方法论
- [Geedea《论遣词造句》](https://www.geedea.pro/essays/on-wording/) — 精确用词、避免欧化中文
- [中文文案排版指北](https://github.com/sparanoid/chinese-copywriting-guidelines) — 排版空格、标点、大小写

## 许可

MIT
