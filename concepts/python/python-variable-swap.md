---
title: Python变量交换案例 — 总览（MOC）
created: 2026-09-06
updated: 2026-09-06
type: moc
tags: [python, python/basics, summary, course]
sources: [课程：黑马程序员]
confidence: high
related: [variable-swap-direct-assignment-trap, temp-variable-swap, three-variable-swap-exercise, python-identifiers-naming]
---

# Python变量交换案例 — 总览

> 来源：黑马程序员 Python 入门课 · 变量交换案例。
> 原始讲稿（sha256: `d0d627a6c26a2361a74a6a7edb8f219c6f3e2fa3fd903a3db75c66abd8de9688`）：^[raw/transcripts/heimahot-variable-swap-case.md]

## 需求

两个变量 `a=10, b=20`，交换两者的值后输出。

## 纯文本全要素框架

```text
┌─────────────────────────────────────────────────────────────┐
│  变量交换案例（黑马程序员）                                    │
├─────────────────────────────────────────────────────────────┤
│ 需求     │ a=10, b=20 → 交换 → a=20, b=10                     │
├──────────┼──────────────────────────────────────────────────┤
│ 错误思路 │ a=b; b=a → a、b 都变成 20（原值 10 丢失）           │
│          │ 原因：赋值是覆盖式复制，不是绑定关系                  │
├──────────┼──────────────────────────────────────────────────┤
│ 生活类比 │ 雪碧/可乐互换 → 必须借第三个空杯子                    │
│          │ 变量 = 装数据的容器，同理借第三个变量                  │
├──────────┼──────────────────────────────────────────────────┤
│ 正确解法 │ ① c=a（存原值）② a=b（覆盖）③ b=c（回填）           │
│          │ c 是临时变量，只负责临时记录 a 的原值                 │
├──────────┼──────────────────────────────────────────────────┤
│ 验证     │ print(a,b) → 20 10 ✓                              │
├──────────┼──────────────────────────────────────────────────┤
│ 课后练习 │ a=100,b=200,c=300；A→C、B→A、C→B 轮转               │
│          │ 解：t=a; a=b; b=c; c=t → 200 300 100 ✓            │
└──────────┴──────────────────────────────────────────────────┘
```

## 代码（完整可运行）

```python
# 案例：两变量交换
a = 10
b = 20

c = a   # 临时变量 c 记录 a 的原值
a = b   # a 拿到 b 的值
b = c   # b 拿回 a 的原值

print(a, b)   # 20 10
```

## 原子笔记

- [[variable-swap-direct-assignment-trap]] — 为什么 `a=b; b=a` 是错的（覆盖式赋值）
- [[temp-variable-swap]] — 临时变量三步法 + 杯子类比
- [[three-variable-swap-exercise]] — 课后练习：三变量轮转（含已验证答案）

## 可视化

- 思维导图 → [[python-variable-swap-mindmap]]
- 知识图谱 → [[python-variable-swap-graph]]

## 关联笔记

- [[python-identifiers-naming]] — 前置知识：变量与命名规范（本课的上半部分）
- [[python-identifier]] — 变量即容器的定义
