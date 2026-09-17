---
title: Python 标识符命名规则（4条强制）
created: 2026-09-06
updated: 2026-09-06
type: concept
tags: [python, python/basics, python/naming, concept, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-identifier, python-keywords, pep8-style-guide, snake-case-naming]
---

# Python 标识符命名规则（4条强制）

> 这是**规则**，不是建议。违反任何一条，代码直接报错。

#python/basics #python/naming

## 规则1：字符组成限制

| 类型 | 范围 |
|------|------|
| 字母 | 大写 A-Z、小写 a-z |
| 数字 | 0-9 |
| 特殊符号 | **仅允许下划线 `_`** |

**核心结论**：下划线是标识符中唯一合法的特殊符号，`$`、`@`、`#`、`%`、`&` 等全部不允许。

## 规则2：开头字符限制

- **禁止**：绝对不能以数字开头
- **允许**：字母开头、下划线开头
- **补充**：下划线开头的数量没有限制，`_name`、`__name` 都合法

## 规则3：关键字禁用

不能使用 Python 关键字作为标识符 → 详见 [[python-keywords]]

## 规则4：大小写严格区分

Python 标识符对大小写**敏感**，`age`、`Age`、`AGE` 是 3 个完全独立的变量。

## 合法性案例集

### 合法标识符

| 类型 | 示例 |
|------|------|
| 纯小写字母 | `name` |
| 含大写字母 | `Name`、`NAME` |
| 下划线开头 | `_name`、`__name` |
| 下划线中间/结尾 | `name_name`、`name_` |
| 含数字（非开头） | `name6` |
| 小写非关键字 | `true` |

### 非法标识符

| 示例 | 违反规则 |
|------|----------|
| `name$` | 规则1：字符组成限制 |
| `and`、`or`、`False` | 规则3：关键字禁用 |
| `6name` | 规则2：开头限制 |

### 易混点

| 标识符 | 合法性 | 原因 |
|--------|--------|------|
| `true`（小写 t） | ✅ 合法 | 不是 Python 关键字 |
| `True`（大写 T） | ❌ 非法 | 是 Python 布尔关键字 |

## 合法性验证方法

```
定义变量 + 输出 → 运行代码 → 判断结果
├─ 能正常运行、输出结果 → 合法标识符
└─ 运行报错、编辑器标红 → 非法标识符
```

**示例1：验证小写 `true`**

```python
true = 1
print(true)
# 正常运行，输出 1 → 合法
```

**示例2：验证大写 `True`**

```python
True = 1  # 报错！
print(True)
# 语法错误：不能为 True 分配值
# True 是布尔类型字面量/关键字，不能作为变量名
```

**示例3：验证 `6name`**

不用运行，编辑器直接标红 —— 违反「不能以数字开头」。

> 实操建议：打开 Python 环境动手验证，或看编辑器的实时报错提示。

## 关联概念

- [[python-identifier]] — 标识符是什么
- [[python-keywords]] — 规则3 涉及的完整关键字清单
- [[pep8-style-guide]] — 满足规则之后，怎么命名才算「好」
- [[snake-case-naming]] — 多单词命名的具体写法
- [[python-identifiers-naming]] — 本课总览（MOC）
