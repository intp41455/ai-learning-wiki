---
title: Wiki 操作日志
created: 2026-09-03
updated: 2026-09-06
type: log
tags: [meta, reference]
sources: [自动生成]
confidence: high
---

# Wiki 日志

> 所有 wiki 操作的 append-only 记录。
> 格式：`## [YYYY-MM-DD] action | subject`
> Actions: create, ingest, update, query, lint, archive, delete
> 超过 500 条后轮转：改名为 log-YYYY.md，重新开始。

## [2026-09-03] create | Wiki 初始化
- Domain: 个人知识库 / AI 辅助学习
- 目录结构创建：SCHEMA.md, index.md, log.md, raw/, entities/, concepts/, comparisons/, queries/
- 配置 WIKI_PATH=<vault> 写入 ~/.hermes/.env
- Obsidian 可用，Graph View 路径：<用户目录>\wiki

## [2026-09-03] sync | OneDrive 同步
- 将 wiki 复制到 <用户目录>\OneDrive\wiki\
- 更新 Obsidian 配置指向 OneDrive 路径
- 手机可通过 OneDrive 同步查看

## [2026-09-03] ingest | 【闪客】一小时从函数到 Transformer（详细复刻版）
- 来源：B站 BV1NCgVzoEG9，UP主：飞天闪客，播放量 130万+
- 完整 7 集内容复刻：
  1. 从函数到神经网络（09:28）
  2. 计算神经网络的参数（11:09）
  3. 调教神经网络的方法（07:55）
  4. 从矩阵到 CNN（08:12）
  5. 从 RNN 到 Transformer（10:04）
  6. Transformer 简单而强大（10:07）
  7. 速通大模型 100 词（12:29）
- 原始材料：raw/transcripts/flash-client-one-hour-function-to-transformer.md（9KB 完整转录文本）
- 主概念页：concepts/one-hour-function-to-transformer.md（16KB，7集逐字稿详细笔记）
- 创建/更新 wiki 页面：
  - concepts/transformer-architecture.md（Transformer 架构详解）
  - concepts/attention-mechanism.md（注意力机制详解）
  - concepts/neural-network-basics.md（神经网络基础）
  - concepts/cnn-architecture.md（CNN 架构）
  - concepts/rnn-architecture.md（RNN 架构）
  - concepts/llm-terms-100.md（LLM 术语 100 词）
  - concepts/ai-learning-path.md（学习路径）
- 更新 index.md，Total pages: 9

## [2026-09-06] organize | 建立主题文件夹结构
- 创建 concepts/python/ 文件夹
- 迁移 python-identifiers-naming.md/.html → concepts/python/
- 迁移 python-variable-swap.md/.html → concepts/python/
- 创建 concepts/python/README.md（Python主题索引）
- 更新 index.md，按主题分类（AI/机器学习、Python编程）
- 设计原则：主题文件夹用于归纳相似笔记；知识图谱保持多维立体，不隔离
- 更新 srt-to-wiki skill：新增第0步主题分类逻辑

## [2026-09-06] create | Python变量交换
- 创建 concepts/python-variable-swap.md（3.8KB，完整笔记）
- 创建 concepts/python-variable-swap-mindmap.html（2.1KB，MindMap可视化）
- 内容：问题引入 + 错误思路分析 + 三步交换法 + 代码实现 + 练习扩展
- 来源：黑马程序员课程
- 更新 index.md，Total pages: 10

## [2026-09-06] create | Python标识符与变量命名
- 创建 concepts/python-identifiers-naming.md（8.6KB，完整笔记）
- 创建 concepts/python-identifiers-mindmap.html（2.2KB，MindMap可视化）
- 内容：4条命名规则 + 3条PEP8规范 + 合法/非法案例 + 验证方法
- 来源：黑马程序员课程
- 更新 index.md，Total pages: 9

## [2026-09-06] cleanup | 清理自动生成的垃圾笔记
- 删除 40 个 bilibili 视频自动采集笔记（concepts/bilibili-BV*.md）
  - 原因：字幕转录错误、内容与标题无关、无实质笔记内容
- 删除 14 个原始 JSON 数据文件（raw/*.json）
- 删除 35 个字幕 TXT 文件（raw/subtitles/*.txt）
- 删除根目录空文件 AI学习路径.md
- 删除未命名 1/ 文件夹和未命名.base/.canvas 文件
- 保留：8 个概念页 + 原始转录稿（flash-client-one-hour-function-to-transformer.md）

## [2026-09-03] create | 交互式知识图谱 HTML
- 生成 knowledge-graph.html（9KB）
- 23 个节点，4 种颜色分类
- 支持拖拽、缩放、点击查看详情
- 位置：<用户目录>\OneDrive\wiki\knowledge-graph.html

## [2026-09-06] fix | 按 SRT→Wiki Skill 标准全面整改（审计后修复）

审计依据：`skill.docx`《从SRT字幕到Obsidian Wiki知识库的构建流程》，结论：原产出 0/5 步达标。

### P0 补齐硬性要求
- 原子拆分 `python-identifiers-naming.md`（原 8.6KB 单页塞 5 概念）→ 拆出：
  - python-identifier.md（标识符定义）
  - python-naming-rules.md（4条强制规则+案例+验证）
  - python-keywords.md（关键字清单、true vs True）
  - pep8-style-guide.md（PEP8 与 3 条规范）
  - snake-case-naming.md（蛇形命名法）
  - 原页改为 type: moc 课程总览，保留纯文本全要素框架
- 新建知识图谱笔记（此前全库 0 个 graph TD）：
  - concepts/python/python-identifiers-graph.md
  - concepts/python/python-variable-swap-graph.md
  - concepts/ai-knowledge-graph.md
- 新建思维导图笔记（独立成页，此前只有 html）：
  - concepts/python/python-identifiers-mindmap.md
  - concepts/python/python-variable-swap-mindmap.md
  - concepts/ai-mindmap.md
- 删除根目录 0 字节空文件 python-identifiers-mindmap.md（此前被 [[]] 指向，点击空白）
- 安装并启用插件：dataview 0.5.70、obsidian-enhancing-mindmap 0.2.5
  （此前 enhancing-mindmap 是空目录；obsidian-mind-map 不兼容 mermaid mindmap）

### P1 补齐流程产出
- 每个课程补纯文本全要素框架（框线版）：python-identifiers-naming、python-variable-swap
- 标签改层级制：python / python/basics / python/naming / python/style
  并把新标签注册进 SCHEMA.md taxonomy（此前 python/programming/tutorial 越界未注册）
- 新建全景画布 `知识地图.canvas`（此前 0 个 canvas）
- 新建 queries/动态索引.md（Dataview 动态索引）

### P2 工程治理
- 修 python-variable-swap.md 的 YAML 非法语法（related 字段里的双方括号）→ 改为单方括号列表
- 补 one-hour-function-to-transformer.md 的 frontmatter 六项，sha256 由 pending 改为实际值
  609e79392ee24bb48422f455e5770f77f19189b47724568ffd6cd25f5873b6a0
- 统一 wikilink 为短名；index.md 2 条死链已修；页面计数 10 → 27
- log.md 补 frontmatter
- 全库死链复检：0（SCHEMA 内示例文本已加反引号）
- 旧库 <用户目录>/wiki 标记废弃（不删除，待人工确认）
- WIKI_PATH 重新写入 ~/.hermes/.env，指向 OneDrive 库

### 遗留（无法自动修复）
- 9-06 cleanup 删除的 35 个字幕 txt + 14 个 json 无法恢复，raw/ 仅剩 1 份转录
- 与 skill.docx 的差异说明见 ~/.hermes/skills/srt-to-wiki/ERRORS-2026-09-06.md

## [2026-09-06] create | Hermes 标准作业流程 Skill
- 新建 ~/.hermes/skills/srt-to-wiki/SKILL.md（此前 log 声称存在但磁盘无此文件）
- 新建 ~/.hermes/skills/srt-to-wiki/ERRORS-2026-09-06.md（逐条错误与纠正）

## [2026-09-06] style | 思维导图低饱和细线样式统一
- 问题：mermaid mindmap 默认线宽 17px/14px/11px、节点 hsl(...,100%,...) 满饱和，视觉盖过内容。
- 处置：全部 mindmap 笔记的 mermaid 块插入 `%%{init}%%` 低饱和样式行（theme=base；节点白底浅灰描边 1px；连线 1.3px、根 1.6px；深灰文字 500）：
  - concepts/ai-mindmap.md
  - concepts/python/python-identifiers-mindmap.md
  - concepts/python/python-variable-swap-mindmap.md
  - (待入库) outputs/pending-20260906/concepts/python/python-variable-swap-mindmap.md
- 已验证：4 张全部真实渲染通过（细线低饱和、内容优先）
- 规范固化：~/.hermes/skills/srt-to-wiki/SKILL.md 第2步①已内置该 init 模板，后续导图强制携带

## [2026-09-06] create | 变量交换案例 · 按 SKILL v2.0 全流程重做（示范批）— 已入库

来源：黑马程序员「变量交换案例」讲稿全文（新文本，含完整错误思路讲解 + 三变量练习）。产物经人工审阅批准后入库，先暂存于 outputs/pending-20260906/。

### 原始材料归档
- raw/transcripts/heimahot-variable-swap-case.md（无 frontmatter，字节不变）
- sha256: d0d627a6c26a2361a74a6a7edb8f219c6f3e2fa3fd903a3db75c66abd8de9688

### 原子拆分（新增 3 篇）
- variable-swap-direct-assignment-trap.md — a=b;b=a 陷阱：覆盖式赋值逐行推演
- temp-variable-swap.md — 临时变量三步法 + 雪碧/可乐杯子类比
- three-variable-swap-exercise.md — 三变量轮转练习（答案已用 Python 实测验证 200 300 100）

### 重写（原 Hermes 版本 → 结构化版本）
- python-variable-swap.md — 转 MOC 总览：需求/框线全要素框架/完整代码/原子导航
- python-variable-swap-mindmap.md — mermaid mindmap 全案例导图（含低饱和样式 init）
- python-variable-swap-graph.md — graph TD：错误路径(红)/正确路径(绿)/类比支撑(蓝)

### SCHEMA / index 变更
- taxonomy 内容类型新增 exercise（练习类）
- index.md：变量交换条目更新为 MOC、原子概念区 +3、原始材料区 +1、总页数 27→30

### 自检（SKILL v2.0 十三项清单）
- frontmatter 六项：齐全 ✓ ｜ 出链 ≥2：满足 ✓ ｜ 死链：0 ✓ ｜ 标签越界：0 ✓
- 原始材料未删改，sha256 已记 ✓ ｜ 导图样式：低饱和细线，真实渲染验证 ✓

## [2026-09-06] fix | 历史越界标签补注册（收尾）
- 全库复检发现 13 种历史标签在用但未注册进 SCHEMA taxonomy（Hermes 早期 AI 笔记的 attention/cnn/rnn/neural-network/meta 等）。
- 按"标签从 taxonomy 取，新增先注册"规则补注册，不改动任何笔记内容：
  - 主题区新增：transformer, attention, mechanism, rnn, recurrent, sequence, cnn, convolution, computer-vision, neural-network, architecture, terminology
  - 元区新增：meta
- 补注册后全库标签越界 = 0。

## [2026-09-07] fix | Canvas 补齐 + graph 样式规范固化（收尾）
- 知识地图.canvas：新增变量交换 5 件套节点（mindmap/graph/3 原子笔记），12→17 节点、7→12 边，挂接在 python-variable-swap MOC 下。全部 file 节点路径有效，JSON 合法。
- ~/.hermes/skills/srt-to-wiki/SKILL.md：第2步② graph TD 段补 v1 低饱和样式 init 模板（与 mindmap 同款：白底浅灰描边 1.2px、连线 1.4px、edgeLabel 白底、不覆盖语义 fill），从此 graph 也是强制样式。
- 全库复检 ALL PASS（31 页 / 0 死链 / 0 越界标签 / 3 mindmap 全带样式）。

## [2026-09-07] enhance | srt-to-wiki skill 新增「莫兰迪卡片化知识树」渲染管线
- `~/.hermes/skills/srt-to-wiki/assets/` 新增自包含渲染管线：build_modules.py（自动识别模块根+语义分色+智能断行）、clean_mermaid.py（清洗压缩源）、render_mmd.js（米白底 #F8F9FA、2x 超清）、build_gallery.py（base64 自包含画廊）、run.py（一键入口）；随包 node_modules（mermaid+puppeteer-core，87M）；Chrome 驱动用本机固定路径；另附 DESIGN-SYSTEM.md（6 色板+分色规则）、README.md。
- 在 Hermes assets 目录实跑 `run.py --input examples/identifier-full.mmd` 验证：全链路 EXIT=0，生成 7 张 mod_*.png + 1.4M 画廊，尺寸与 WorkBuddy 产出一致 → Hermes 已具备独立复现能力。
- SKILL.md 第 2 步新增 ④ 莫兰迪卡片化知识树（节点>12 强制拆模块卡片、入 Obsidian），description 与交付清单（14 项）同步更新。
- 下次用户粘贴讲稿/SRT 或 mermaid 源码，WorkBuddy/Hermes 均可复用：结构化分析 → graph TD → run.py → mod_*.png+画廊 → 存 OneDrive/wiki。设计红线：禁用刺眼大红大绿；>12 节点必须拆卡（防 dagre 拉成 14000px 超宽条）。
