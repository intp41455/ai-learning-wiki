---
title: Python 关键字
created: 2026-09-06
updated: 2026-09-06
type: concept
tags: [python, python/basics, python/naming, concept, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-naming-rules, python-identifier, python-naming-legality]
---

# Python 关键字

> 关键字是 Python 内置的、有特殊功能/含义的**保留字**，不能用作标识符。

#python/basics #python/naming

## 为什么不能用作标识符

关键字承担语法功能，一旦被当作变量名，解释器无法区分你是要「用它的语法功能」还是「用它存的数据」，直接语法错误。

## 常见关键字清单（课程提及）

| 类型 | 关键字 |
|------|--------|
| 布尔类型 | `True`、`False` |
| 逻辑运算符 | `and`、`or` |
| 流程控制 | `if`、`else`、`for`、`while` |

## 高频易错点 ⚠️

```
true  → ✅ 合法（小写不是关键字）
True  → ❌ 非法（大写 True 是布尔关键字）
```

**验证代码**

```python
true = 1      # 合法，正常运行
True = 1      # SyntaxError: cannot assign to True
```

大小写是判断关键 —— 见 [[python-naming-rules]] 规则4（大小写敏感）。

## 关联概念

- [[python-naming-rules]] — 关键字禁用是 4 条强制规则中的规则3
- [[python-identifier]] — 标识符的定义
- [[python-identifiers-naming]] — 本课总览（MOC）
