---
title: 三变量轮转交换 — 课后练习与答案
created: 2026-09-06
updated: 2026-09-06
type: exercise
tags: [python, python/basics, exercise, course]
sources: [课程：黑马程序员]
confidence: high
related: [temp-variable-swap, python-variable-swap, variable-swap-direct-assignment-trap]
---

# 三变量轮转交换（课后练习）

## 需求（原题）

三个变量：`a = 100`，`b = 200`，`c = 300`。
将 **A、B、C 的值分别赋值给 C、A、B**，然后输出到控制台。

即目标映射：

| 变量 | 原值 | 新值 = 谁 |
|------|------|-----------|
| a | 100 | 旧 b（200） |
| b | 200 | 旧 c（300） |
| c | 300 | 旧 a（100） |

三个值沿 a→c→b→a 的方向**轮转一圈**。

## 思路

与两变量交换同构：覆盖发生前，先把**唯一会被覆盖且无处可去的原值**（a）存进临时变量 t，然后按"从后往前接"的顺序依次覆盖。

## 参考答案（已验证）

```python
a, b, c = 100, 200, 300

t = a   # t 记录 a 的原值 100
a = b   # a = 200
b = c   # b = 300
c = t   # c = 100

print(a, b, c)   # 输出: 200 300 100
```

验证结果：`a=200, b=300, c=100`，与需求映射一致 ✅

## 易错点

- 顺序错（如先 `a = b` 再 `t = a`）→ a 的原值 100 在第一步就丢了，落回 [[variable-swap-direct-assignment-trap|直接赋值陷阱]]
- 误以为需要多个临时变量 → 三个值轮转一圈，**一个临时变量就够**，因为任一时刻只有一个原值"无家可归"

## 关联笔记

- [[temp-variable-swap]] — 两变量版的标准解法（本题的方法源头）
- [[variable-swap-direct-assignment-trap]] — 为什么不能直接赋值
- [[python-variable-swap]] — 案例总览（MOC）
