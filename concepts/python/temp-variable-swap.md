---
title: 临时变量法交换 — 三步交换与杯子类比
created: 2026-09-06
updated: 2026-09-06
type: technique
tags: [python, python/basics, technique, course]
sources: [课程：黑马程序员]
confidence: high
related: [variable-swap-direct-assignment-trap, three-variable-swap-exercise, python-variable-swap]
---

# 临时变量法交换

## 生活类比：雪碧与可乐

两只杯子，一杯装雪碧（a=10），一杯装可乐（b=20），要互换饮料，必须**借第三个空杯子**：

1. 雪碧倒进空杯 → 第一杯空了（`c = a`）
2. 可乐倒进第一杯 → 第二杯空了（`a = b`）
3. 空杯里的雪碧倒进第二杯（`b = c`）

变量同理：**每个变量都是装数据的容器**，交换两个容器里的数据，同样要借助第三个容器。

## 标准三步（初始 a=10, b=20）

```python
a = 10
b = 20

c = a   # 第1步：用 c 记录 a 的原值（c=10）
a = b   # 第2步：a 拿到 b 的值（a=20，此时 b 的原值已被 a 接住，不会丢）
b = c   # 第3步：b 拿回 a 的原值（b=10）

print(a, b)   # 输出: 20 10  ← 交换成功
```

## 逐步推演表

| 步骤 | 代码 | a | b | c | 说明 |
|------|------|-----|-----|-----|------|
| 初始 | — | 10 | 20 | — | — |
| 1 | `c = a` | 10 | 20 | **10** | a 的原值被安全存进 c |
| 2 | `a = b` | **20** | 20 | 10 | a 覆盖，但原值已在 c 里 |
| 3 | `b = c` | 20 | **10** | 10 | b 拿回 a 的原值 |

## 为什么第 3 步是 `b = c` 而不是 `b = a`

走到第 3 步时 **a 已经变成 20**，`b = a` 拿到的是错的值；只有 c 里还存着原始的 10。这正是 [[variable-swap-direct-assignment-trap|直接赋值陷阱]] 的教训——先用 c 保住原值，覆盖就不可怕了。

## 关键认知

- c 是**临时变量**：不属于需求本身，只为"临时记录 a 的原值"而存在，用完即可丢
- 顺序不可乱：必须**先保存、再覆盖、最后回填**（保存 → 覆盖 → 回填）
- 该模式可推广到 N 个变量的循环交换 → [[three-variable-swap-exercise]]

## 关联笔记

- [[variable-swap-direct-assignment-trap]] — 不用临时变量会怎样
- [[three-variable-swap-exercise]] — 推广到三变量的轮转练习
- [[python-variable-swap]] — 案例总览（MOC）
