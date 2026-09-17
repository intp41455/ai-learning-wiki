---
title: Python标识符与变量命名 — 思维导图
created: 2026-09-06
updated: 2026-09-06
type: mindmap
tags: [python, python/basics, python/naming, summary, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-identifiers-naming, python-identifiers-graph]
---

# Python标识符与变量命名 — 思维导图

> 阅读模式下由 Enhancing Mindmap / Obsidian 内置 mermaid 渲染。
> 返回总览：[[python-identifiers-naming]]

```mermaid
%%{init: {"theme": "base", "themeVariables": {"primaryColor": "#fafbfc", "primaryTextColor": "#2b3340", "primaryBorderColor": "#cfd6df", "lineColor": "#a8b3bf", "fontFamily": "-apple-system, Segoe UI, PingFang SC, Microsoft YaHei, sans-serif", "fontSize": "13px"}, "themeCSS": ".mindmap-node .background{fill:#ffffff !important;stroke:#cfd6df !important;stroke-width:1px !important}.mindmap-node.section-0 .background{fill:#eef4fb !important;stroke:#b6cad9 !important}.mindmap-node.section-2 .background{fill:#fafbfc !important}.edge{fill:none !important;stroke:#a8b3bf !important;stroke-width:1.3px !important}.edge.section-edge-0{stroke:#7a8a99 !important;stroke-width:1.6px !important}.text-inner-tspan,.text-outer-tspan{fill:#2b3340 !important;font-weight:500 !important}.mindmap-node{padding:6px}"}}%%
mindmap
  root((Python标识符<br/>与变量命名))
    标识符基础
      官方定义：开发人员命名元素
      覆盖范围：变量/函数/类
      现阶段理解：等同于变量名
      规则性质：硬性规定
    4条命名规则
      规则1：仅字母/数字/下划线
        允许：A-Z a-z 0-9 _
        禁止：$ @ # % &
      规则2：不能数字开头
        允许：字母开头
        允许：下划线开头
      规则3：禁用关键字
        如：True False and or if
        易错：true合法 vs True非法
      规则4：区分大小写
        示例：age ≠ Age ≠ AGE
    案例集
      合法：name / Name / _name / name6 / true
      非法：name$ / 6name / and / False
    验证方法
      定义变量加运行看结果
      编辑器标红即非法
    命名规范PEP8
      见名知意
        正例：name age color
        反例：a a1 b c
      蛇形命名法
        正例：update_time my_name
        反例：updateTime myName
      全小写
    核心考点
      4条规则必须背
      3条规范建议遵守
```

## 关联

- [[python-identifiers-naming]] — 课程总览
- [[python-identifiers-graph]] — 同一内容的知识图谱版本
- [[python-identifier]] / [[python-naming-rules]] / [[python-keywords]] / [[pep8-style-guide]] / [[snake-case-naming]]
