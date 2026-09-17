---
title: 蛇形命名法
created: 2026-09-06
updated: 2026-09-06
type: concept
tags: [python, python/basics, python/style, technique, course]
sources: [课程：黑马程序员]
confidence: high
related: [pep8-style-guide, python-naming-rules, python-identifier]
---

# 蛇形命名法

> 变量名由多个单词组成时，单词之间用下划线 `_` 分隔：`user_first_name`。

#python/basics #python/style

## 核心规则

- **适用场景**：变量名由多个单词/多个部分组成时
- **写法**：多个单词之间用下划线分隔，**两两之间都要加**

## 正例 vs 反例

| 变量名 | 含义 | 评价 |
|--------|------|------|
| `update_time` | 更新时间 | ✅ 蛇形 |
| `my_name` | 我的名字 | ✅ 蛇形 |
| `user_first_name` | 用户的名字 | ✅ 蛇形 |
| `updateTime` | 更新时间 | ❌ 驼峰，Python 变量不推荐 |
| `myName` | 我的名字 | ❌ 驼峰，Python 变量不推荐 |

## 配套规范

- 字母**全部小写**（见 [[pep8-style-guide]] 规范3）
- 下划线本来就是标识符中唯一合法的特殊符号（见 [[python-naming-rules]] 规则1）

## 关联概念

- [[pep8-style-guide]] — 蛇形命名是 PEP8 规范2
- [[python-naming-rules]] — 下划线合法性的规则依据
- [[python-identifier]] — 标识符的定义
- [[python-identifiers-naming]] — 本课总览（MOC）
