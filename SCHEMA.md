---
domain: 个人知识库 / AI 辅助学习
conventions:
  - 文件名全小写、连字符、无空格
  - 每页必须有 YAML frontmatter（title / created / updated / type / tags / sources）
  - 用双链语法（双方括号）双向链接，每页至少 2 个出链
  - 标签从下方 taxonomy 取，新增标签先加到 taxonomy
  - 标签必须用层级制（如 python/basics），正文用 #python/basics 行内标签
  - 一个笔记只讲一个概念（原子笔记）；课程总览用 type: moc
  - YAML 里禁止写双链语法（方括号嵌套在 YAML 里是嵌套数组，非法），写 `related: [note-name]`
  - provenance: 3+ 来源综合的段落末尾加 ^[raw/.../source.md]
  - 原始材料（SRT/字幕/转录）一律归档到 raw/，**禁止删除**
  - raw/ 下的原始材料保持字节不变（不写 frontmatter），否则 sha256 失效；元信息写在引用它的笔记里
  - confidence: high | medium | low；opinion-heavy 或单来源必须标
  - 更新时 bump `updated`，所有动作记入 log.md
page_thresholds:
  create: 出现 2+ 次或为核心主题
  add_to_existing: 已有页面覆盖的内容
  dont_create: 仅一次提及的细节
  split: 超过 200 行
  archive: 被完全替代 → 移入 _archive/
frontmatter_required: [title, created, updated, type, tags, sources]
type_allowed: [concept, moc, mindmap, graph, transcript, index, topic-index, summary]
confidence_levels: [high, medium, low]
contested: true
wiki_path: C:\Users\intpj\OneDrive\wiki
deliverables_per_course:
  - 结构化清单（层级 + 关联）
  - 原子笔记（每个核心概念一个）
  - 思维导图笔记（mermaid mindmap）
  - 知识图谱笔记（mermaid graph TD）
  - 纯文本全要素框架（框线版，放 MOC 或主笔记）
required_plugins: [dataview, obsidian-enhancing-mindmap, canvas(核心插件)]
---

# 标签分类体系

## 主题
- ai, machine-learning, deep-learning, llm, prompt-engineering, rag
- python, python/basics, python/naming, python/style
- transformer, attention, mechanism, rnn, recurrent, sequence, cnn, convolution, computer-vision, neural-network, architecture, terminology

## 学习
- learning, study-method, productivity, tool, workflow, video-notes

## 内容类型
- concept, entity, comparison, summary, framework, technique, exercise, moc, mindmap, graph, index

## 来源
- bilibili, youtube, paper, book, article, course, transcript

## 元
- todo, reference, question, insight, meta

---

## 给 Agent（Hermes / 其他）的入口

整理笔记前必须先读这两份文件：

- `~/.hermes/skills/srt-to-wiki/SKILL.md` — 标准作业流程（5 步 + 13 项自检）
- `~/.hermes/skills/srt-to-wiki/ERRORS-2026-09-06.md` — 历史错误清单，别再犯
- `~/.hermes/skills/srt-to-wiki/EXAMPLE-DEMO-20260906.md` — 满分示范批：先暂存审阅、批准后入库，照抄结构

参考样例：`concepts/python/` 下的一整套（MOC + 原子笔记 + 导图 + 图谱）。
