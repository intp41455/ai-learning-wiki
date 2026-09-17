---
title: 注意力机制
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [attention, transformer, mechanism, deep-learning, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# 注意力机制（Attention Mechanism）

> 基于闪客《一小时从函数到 Transformer》第 06 集详细复刻

## 直觉类比
注意力机制的底层直觉是 **"软查询"**：当前词元（Query）去问序列里所有词元（Key），看谁和它最相关，然后从对应的词元（Value）那里提取信息。

**类比图书馆查书**：
- Query = 你脑子里想找的主题
- Key = 书脊上的标签
- Value = 书里的实际内容

## Scaled Dot-Product Attention（缩放点积注意力）

```
Attention(Q, K, V) = softmax(QK^T / √d_k) · V
```

| 符号 | 含义 | 闪客讲解 |
|------|------|---------|
| Q (Query) | 当前词元"想问什么" | "我和谁相关？" |
| K (Key) | 每个词元"能回答什么" | "我能被谁关注？" |
| V (Value) | 每个词元"实际提供的信息" | "我提供什么信息？" |
| d_k | Key 向量的维度 | 维度越大，点积方差越大 |
| √d_k | 缩放因子 | 防止 softmax 饱和，保持梯度稳定 |

### 为什么需要缩放？
当 d_k 较大时，Q·K 的点积方差变大，softmax 进入梯度极小的饱和区。除以 √d_k 把方差拉回 1，保持梯度稳定。

## Multi-Head Attention（多头注意力）

```
MultiHead(Q, K, V) = Concat(head_1, ..., head_h) · W^O
head_i = Attention(Q·W^Q_i, K·W^K_i, V·W^V_i)
```

- h 个注意力头并行计算，每个头学习不同的关系模式
- 类比：一组专家从不同维度分析同一份材料
- 闪客比喻：就像一组专家分别看语法、语义、指代等不同维度，最后综合判断

## Masked Attention（掩码注意力，解码器专用）
- 在 Q·K^T 之后，把上三角位置设为 -∞
- Softmax 后这些位置概率为 0
- 保证生成时只能"看到"已生成的词，不能偷看未来

## Cross-Attention（交叉注意力，解码器看编码器）
- Q 来自解码器当前层
- K、V 来自编码器最终输出
- 让解码器的每个生成步骤都能参考输入序列的全部信息

## 注意力权重可视化
- 注意力矩阵是 n×n 的权重图
- 每个位置 i 对位置 j 的关注度 = softmax 后的权重
- 热力图展示：语法关系（主谓一致）、指代（it → cat）、短语边界等

## 从 RNN 到 Attention 的演进

| 模型 | 核心机制 | 优势 | 劣势 |
|------|---------|------|------|
| RNN | 顺序处理，带隐藏状态 | 能处理变长序列 | 梯度消失、无法并行、长距离依赖弱 |
| LSTM/GRU | 门控机制，选择性记忆 | 缓解梯度消失 | 仍有顺序依赖，并行性差 |
| Transformer | 全局 Self-Attention | 完全并行、长距离依赖、可解释性强 | 计算量 O(n²)、需要大量数据 |

## 闪客讲解要点
1. Attention 本质是"软查询"——不是硬匹配，而是加权混合
2. Q/K/V 三分法让"问什么"和"答什么"解耦
3. 缩放因子 √d_k 是容易被忽略但关键的设计
4. 多头注意力让模型能同时关注多种关系模式

## 与相关概念的联系

- [[transformer-architecture]]：Self-Attention 是 Transformer 的核心
- [[one-hour-function-to-transformer]]：闪客视频中的讲解来源，第 06 集
- [[neural-network-basics]]：函数与参数的基础，第 01-03 集
- [[ai-learning-path]]：完整 AI 学习路线

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
