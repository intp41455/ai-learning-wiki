# CLAUDE.md

本仓库是 **AI 学习知识库**（Obsidian vault），按工程规范组织：49 篇原子笔记 / 11.3 万字，覆盖 Transformer、注意力机制、CNN、RNN、LLM 术语、Python 规范。核心价值在于知识被结构化、可追溯、可自动生产，而非笔记数量。

## 1. 项目目的

外部材料（视频 / 网页 / PDF / 推文）→ 抓取 → 归档原文 → 提炼原子笔记 → 建双链 → 成知识图谱。每门课程固定交付 5 种产物：结构化清单、原子笔记、思维导图（mermaid mindmap）、知识图谱（mermaid graph TD）、纯文本全要素框架。

## 2. 技术栈

- **Obsidian**（Markdown vault + 双链 + Canvas + Dataview 查询）
  - 必需插件：`dataview`、`obsidian-enhancing-mindmap`、`canvas`（见 `SCHEMA.md` frontmatter `required_plugins`）
- **Markdown**：YAML frontmatter、`[[双链]]`、`#python/basics` 层级标签、mermaid
- **HTML**：静态力导向知识图谱（`knowledge-graph.html`）、mermaid 导图产物
- **Obsidian Canvas**（`.canvas` JSON）：`知识地图.canvas` 全景地图
- **Copilot skills**（`copilot/skills/`）：5 个抓取 skill（youtube-transcript / web-fetch / read-pdf / fetch-x / web-search）+ 5 个 Obsidian 能力 skill（json-canvas / obsidian-bases / obsidian-cli / obsidian-markdown / openartifacts-publish），每个 skill 带 `.cmd` / `.ps1` / `.sh` 三平台脚本

## 3. 目录结构

```
.
├── SCHEMA.md              # 规范源头：12 条强制约定 + 标签 taxonomy + 页面创建判据
├── index.md               # 总索引（手动维护）
├── log.md                 # 操作日志（append-only，格式 `## [YYYY-MM-DD] action | subject`）
├── knowledge-graph.html   # 知识图谱（静态生成，深色力导向图，可交互）
├── 知识地图.canvas         # Obsidian Canvas 全景地图
├── concepts/              # 原子笔记 + MOC + 导图/图谱
│   ├── transformer-architecture.md / attention-mechanism.md / …（AI 主题）
│   └── python/            # Python 主题子目录（MOC + 原子笔记 + .md/.html 导图图谱）
├── raw/                   # 原始材料（transcripts/、subtitles/）—— 字节不变，禁止删除
├── queries/动态索引.md     # Dataview 自动查询
├── Tags/                  # 标签体系（目录形式，如 Tags/#python+basics/）
├── copilot/skills/        # 抓取与 Obsidian 能力 skill
└── docs/architecture.*    # 架构图（png + 交互 html + 规格 json）
```

## 4. 安装 / 运行（无构建、无测试）

本仓库是知识库，没有构建或测试流程。使用方式：

1. 装 Obsidian，把本目录（或镜像 `C:\Users\intpj\OneDrive\wiki`，见 SCHEMA `wiki_path`）作为 vault 打开
2. 启用三个插件：`dataview`、`obsidian-enhancing-mindmap`、`canvas`
3. 浏览器直接打开 `knowledge-graph.html` 看图谱；打开 `知识地图.canvas` 看主题聚类

抓取 skill 直接执行 `copilot/skills/<name>/` 下对应平台的脚本（`.ps1` Windows / `.sh` Unix / `.cmd` 快捷入口），无需安装依赖。

## 5. 关键约定与坑点（改笔记前必读 `SCHEMA.md`）

- **Frontmatter 必填**：`title` / `created` / `updated` / `type` / `tags` / `sources`；更新内容必须 bump `updated` 并把动作记入 `log.md`
- **YAML 里禁止双链**：`related: [[a]]` 会被 YAML 解析为嵌套数组而非法，必须写 `related: [a, b]`
- **`raw/` 字节不变**：原始材料（转录/字幕）一旦落库不再修改、不写 frontmatter，否则 `sha256` 校验失效；元信息写在引用它的笔记里
- **标签必须来自 taxonomy**：层级制（如 `python/basics`），新增标签先加进 SCHEMA；正文用 `#python/basics`
- **原子性**：一个笔记只讲一个概念；课程总览用 `type: moc`；超过 200 行应拆分
- **溯源**：3+ 来源综合的段落末尾加 `^[raw/.../source.md]`；`confidence: high | medium | low`，观点性或单来源必须降级
- **链接**：双链语法，每页至少 2 个出链
- **页面判据**：出现 2+ 次或核心主题才建页；仅一次提及的细节不建页；被完全替代 → 移入 `_archive/`
- **知识图谱是静态产物**：`knowledge-graph.html` 新增笔记后需重新生成，不会自动更新
- **`provenance` 靠自觉**：规范约束格式，不校验内容正确性
