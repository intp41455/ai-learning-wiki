---
title: PEP8 编码规范
created: 2026-09-06
updated: 2026-09-06
type: concept
tags: [python, python/basics, python/style, concept, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-naming-rules, snake-case-naming, python-identifier]
---

# PEP8 编码规范

> 这是**规范**，不是规则。不遵守代码照样能跑，但会很难维护。

#python/basics #python/style

## 规则 vs 规范

| 类型 | 说明 |
|------|------|
| **规则** | 硬性规定，必须遵守，否则代码报错 → [[python-naming-rules]] |
| **规范** | 官方建议，可遵守也可不遵守，不遵守代码也能运行 |

## PEP 是什么

- **PEP**：Python 社区的技术文档和标准化机制
- **PEP8**：专门描述 Python 代码风格、编码规范的官方文档
- **意义**：提升可读性、降低大型项目维护成本、统一社区风格

## 变量命名的 3 条规范

### 规范1：见名知意

通过变量名就能知道变量存的是什么。

| 正面示例 | 含义 |
|----------|------|
| `name` | 姓名 |
| `age` | 年龄 |
| `color` | 颜色 |

**反面示例**：`a`、`a1`、`a2`、`b`、`c` —— 无意义命名。

**危害**：
- 无法通过变量名判断数据内容
- 几个月后回看代码完全忘记含义
- 注意：无意义命名**合法但不合规**，不报错

### 规范2：蛇形命名法

多个单词用下划线分隔 → 详见 [[snake-case-naming]]

### 规范3：变量名全小写

变量名中的所有英文字母全部使用小写（仅针对变量名，函数/类的命名规范后续单独讲）。

## 学习建议

初期不用死记硬背，先留有印象，写得多了自然记住。

## 关联概念

- [[python-naming-rules]] — 与规范相对的那 4 条硬性规则
- [[snake-case-naming]] — 规范2 的具体写法
- [[python-identifier]] — 被命名的对象
- [[python-identifiers-naming]] — 本课总览（MOC）
