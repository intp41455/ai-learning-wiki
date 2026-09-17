---
title: Python标识符与变量命名 — 知识图谱
created: 2026-09-06
updated: 2026-09-06
type: graph
tags: [python, python/basics, python/naming, summary, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-identifiers-naming, python-identifiers-mindmap]
---

# Python标识符与变量命名 — 知识图谱

> 概念关联网络（graph TD）。返回总览：[[python-identifiers-naming]]

```mermaid
%%{init: {"theme": "base", "themeVariables": {"fontFamily": "-apple-system, Segoe UI, PingFang SC, Microsoft YaHei, sans-serif", "fontSize": "14px", "lineColor": "#9aa6b2", "primaryBorderColor": "#cfd6df", "primaryColor": "#fafbfc", "primaryTextColor": "#1f2329"}, "themeCSS": ".node rect,.node polygon,.node ellipse{stroke:#cfd6df !important;stroke-width:1.2px !important}.edge path{stroke:#9aa6b2 !important;stroke-width:1.4px !important}.edgeMarker{stroke:#9aa6b2 !important;fill:#9aa6b2 !important}.edgeLabel{background-color:#ffffff !important;font-size:12px !important;color:#5a6470 !important;padding:2px 6px !important;border-radius:4px !important;border:1px solid #e4e8ee !important}.label,.nodeLabel{font-family:-apple-system,Segoe UI,PingFang SC,Microsoft YaHei,sans-serif !important}.cluster rect{stroke:#dde3ea !important;stroke-width:1px !important;fill:#fafbfc !important}.note rect,.note polygon{stroke:#d8dde3 !important;stroke-width:1px !important;fill:#fafbfc !important}"}}%%
graph TD
    A[Python标识符与变量命名] --> B[标识符概念]
    B --> B1[定义：给变量/函数/类命名]
    B --> B2[现阶段：等同于变量名]
    B --> B3[性质：硬性规定]

    A --> C[4条强制规则]
    C --> C1[规则1：字符组成]
    C1 --> C11[允许：字母/数字/下划线]
    C1 --> C12[禁止：$ @ # 等符号]
    C --> C2[规则2：开头限制]
    C2 --> C21[禁止数字开头]
    C2 --> C22[允许字母/下划线开头]
    C --> C3[规则3：禁用关键字]
    C --> C4[规则4：大小写敏感]

    C3 --> K[Python关键字]
    K --> K1[布尔：True / False]
    K --> K2[逻辑：and / or]
    K --> K3[流程：if / else / for / while]

    C --> D[案例集]
    D --> D1[合法：name / _name / name6]
    D --> D2[非法：6name / name$ / and]
    C1 --> D2
    C2 --> D2
    C3 --> D2
    D1 -.对比.-> D2

    C --> E[验证方法]
    E --> E1[定义变量加运行看结果]
    E --> E2[编辑器标红即非法]

    A --> F[PEP8 命名规范]
    F --> F1[见名知意]
    F --> F2[蛇形命名法]
    F --> F3[全小写]
    F2 --> S[snake_case 写法]
    S --> S1[正例：update_time]
    S --> S2[反例：updateTime]

    B3 -.规则.-> C
    F -.规范不同于规则.-> C
```

## 关联

- [[python-identifiers-naming]] — 课程总览
- [[python-identifiers-mindmap]] — 同一内容的思维导图版本
- [[python-identifier]] / [[python-naming-rules]] / [[python-keywords]] / [[pep8-style-guide]] / [[snake-case-naming]]
