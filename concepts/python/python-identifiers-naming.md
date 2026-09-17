---
title: Python标识符与变量命名（课程总览）
created: 2026-09-06
updated: 2026-09-06
type: moc
tags: [python, python/basics, python/naming, summary, course]
sources: [课程：黑马程序员]
confidence: high
related: [python-identifier, python-naming-rules, python-keywords, pep8-style-guide, snake-case-naming]
---

# Python标识符与变量命名（课程总览）

> 课程出品：黑马程序员
> 本页是**总览索引（MOC）**，细节已拆分为原子笔记，一个笔记只讲一个概念。

#python/basics #python/naming

## 一、纯文本全要素框架（背诵版）

```
┌─────────────────────────────────────────────────────────┐
│  Python标识符与变量命名                                  │
├─────────────────────────────────────────────────────────┤
│ ▶ 一、标识符基础                                        │
│   1. 定义：开发人员给变量/函数/类起的名字                │
│   2. 现阶段理解：等同于「变量的名字」                    │
│   3. 性质：硬性规定，违反必报错                          │
│ ▶ 二、命名规则（4条强制，必背）                          │
│   规则1 字符组成：字母 + 数字 + 下划线（仅此一种符号）   │
│   规则2 开头限制：禁止数字开头，允许字母/下划线开头      │
│   规则3 关键字禁用：True/False/and/or/if 等不可用        │
│   规则4 大小写敏感：age ≠ Age ≠ AGE                      │
│ ▶ 三、合法性案例                                        │
│   合法：name / Name / _name / name6 / true               │
│   非法：name$ / 6name / and / False                      │
│   易错：true 合法 vs True 非法                           │
│ ▶ 四、验证方法                                          │
│   定义变量 + 运行 → 能输出结果=合法，报错=非法           │
│ ▶ 五、命名规范（PEP8，3条建议）                          │
│   1. 见名知意，拒绝 a/b/c                                │
│   2. 蛇形命名法：多单词用 _ 分隔                         │
│   3. 字母全小写                                          │
└─────────────────────────────────────────────────────────┘
```

## 二、原子笔记索引

| 概念 | 笔记 | 一句话 |
|------|------|--------|
| 标识符是什么 | [[python-identifier]] | 开发人员给变量/函数/类起的名字 |
| 4条强制规则 | [[python-naming-rules]] | 字符组成、开头、关键字、大小写 |
| 关键字清单 | [[python-keywords]] | `True`/`and`/`if` 等保留字，不能当变量名 |
| PEP8 规范 | [[pep8-style-guide]] | 见名知意 + 蛇形 + 全小写 |
| 蛇形命名法 | [[snake-case-naming]] | `user_first_name` 这种写法 |

## 三、可视化

- 思维导图 → [[python-identifiers-mindmap]]
- 知识图谱 → [[python-identifiers-graph]]

## 四、核心考点

**必背（4条强制规则）**
1. 只能包含字母（大小写）、数字、下划线
2. 绝对不能以数字开头
3. 不能使用 Python 关键字
4. 严格区分大小写

**建议遵守（3条规范）**
1. 见名知意，不用 `a`、`b`、`c`
2. 多单词用下划线分隔（蛇形）
3. 英文字母全部小写

## 五、概念关系速查

- [[python-identifier]] 受 [[python-naming-rules]] 约束
- [[python-naming-rules]] 规则3 依赖 [[python-keywords]] 清单
- [[python-naming-rules]] 只管「能不能用」，[[pep8-style-guide]] 管「好不好」
- [[pep8-style-guide]] 规范2 = [[snake-case-naming]]
- 实操案例 → [[python-variable-swap]]
