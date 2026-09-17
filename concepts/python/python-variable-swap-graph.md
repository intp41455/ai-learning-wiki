---
title: Python变量交换案例 — 知识图谱
created: 2026-09-06
updated: 2026-09-06
type: graph
tags: [python, python/basics, framework, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-variable-swap, python-variable-swap-mindmap]
---

# Python变量交换案例 — 知识图谱

> 阅读模式下由 mermaid 渲染（graph TD）。
> 返回总览：[[python-variable-swap]]

```mermaid
%%{init: {"theme": "base", "themeVariables": {"fontFamily": "-apple-system, Segoe UI, PingFang SC, Microsoft YaHei, sans-serif", "fontSize": "14px", "lineColor": "#9aa6b2", "primaryBorderColor": "#cfd6df", "primaryColor": "#fafbfc", "primaryTextColor": "#1f2329"}, "themeCSS": ".node rect,.node polygon,.node ellipse{stroke:#cfd6df !important;stroke-width:1.2px !important}.edge path{stroke:#9aa6b2 !important;stroke-width:1.4px !important}.edgeMarker{stroke:#9aa6b2 !important;fill:#9aa6b2 !important}.edgeLabel{background-color:#ffffff !important;font-size:12px !important;color:#5a6470 !important;padding:2px 6px !important;border-radius:4px !important;border:1px solid #e4e8ee !important}.label,.nodeLabel{font-family:-apple-system,Segoe UI,PingFang SC,Microsoft YaHei,sans-serif !important}.cluster rect{stroke:#dde3ea !important;stroke-width:1px !important;fill:#fafbfc !important}.note rect,.note polygon{stroke:#d8dde3 !important;stroke-width:1px !important;fill:#fafbfc !important}"}}%%
graph TD
    REQ["需求：交换 a=10, b=20"]

    REQ --> WRONG["错误思路<br/>a=b; b=a"]
    WRONG --> WHY["赋值 = 复制值，覆盖式<br/>a 的原值 10 第一步就丢失"]
    WHY --> FAIL["结果 a=b=20 ✗"]

    REQ --> MODEL["心智模型<br/>变量 = 装数据的容器"]
    MODEL --> ANALOGY["生活类比<br/>雪碧/可乐互换 → 借第三个空杯子"]
    ANALOGY --> TEMP["引入临时变量 c"]

    TEMP --> S1["① c = a<br/>记录原值"]
    S1 --> S2["② a = b<br/>安全覆盖"]
    S2 --> S3["③ b = c<br/>回填原值"]
    S3 --> OK["a=20, b=10 ✓"]

    OK --> EX["练习：三变量轮转<br/>a=100,b=200,c=300<br/>A→C, B→A, C→B"]
    EX --> EXA["t=a; a=b; b=c; c=t<br/>→ 200 300 100 ✓"]

    WRONG -.教训.-> TEMP
    MODEL -.支撑.-> TEMP

    style WRONG fill:#fdecec,stroke:#c23531,color:#1f2329
    style FAIL fill:#fdecec,stroke:#c23531,color:#1f2329
    style OK fill:#e8f4ea,stroke:#2f7d4f,color:#1f2329
    style EXA fill:#e8f4ea,stroke:#2f7d4f,color:#1f2329
    style TEMP fill:#eaf0fb,stroke:#3a5bbf,color:#1f2329
```

## 节点与笔记的对应

- 错误思路 → [[variable-swap-direct-assignment-trap]]
- 临时变量三步法 → [[temp-variable-swap]]
- 三变量轮转 → [[three-variable-swap-exercise]]
- 容器心智模型 → [[python-identifier]]
