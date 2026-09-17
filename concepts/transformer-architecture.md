---
title: Transformer 架构
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [transformer, architecture, attention, deep-learning, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# Transformer 架构

> 基于闪客《一小时从函数到 Transformer》第 06 集详细复刻

## 定义
Transformer 是一种基于 **Self-Attention** 的神经网络架构，2017 年 Google Brain 在 "Attention Is All You Need" 论文中首次提出。它完全摒弃了循环和卷积，用纯注意力机制处理序列。

## 核心创新

### 1. Self-Attention（自注意力）
- 每个词元都能直接与序列中所有其他词元交互
- 计算：Attention(Q, K, V) = softmax(QK^T / √d_k) · V
- 复杂度 O(n²)，但完全并行

### 2. Multi-Head Attention（多头注意力）
- 把 Q/K/V 投影到多个子空间，分别做注意力
- 多头输出拼接后线性变换
- 让模型同时关注不同层面的语义关系

### 3. Positional Encoding（位置编码）
- 注入词序信息（Attention 本身是无序的）
- 原始方案：正弦/余弦函数，支持相对位置泛化
- 后续方案：RoPE、ALiBi 等

### 4. Feed-Forward Network（前馈网络）
- 每个 Transformer Block 包含两层全连接 + 激活函数
- 逐位置独立计算，可完全并行

### 5. Layer Normalization + Residual Connection
- 每层输出 = LayerNorm(x + Sublayer(x))
- 残差连接解决梯度消失，LN 稳定训练

## 整体架构

```
输入 → Embedding + 位置编码
    ↓
编码器块 × N（每个：多头注意力 → FFN）
    ↓
中间表示
    ↓
解码器块 × N（每个：掩码注意力 → 交叉注意力 → FFN）
    ↓
输出投影 → Softmax
```

## 编码器 vs 解码器

| 组件 | 作用 | 特点 |
|------|------|------|
| 编码器 | 编码输入序列 | 双向注意力，看到全部输入 |
| 解码器 | 自回归生成输出 | 掩码注意力（只看过去）+ 交叉注意力（看编码器） |
| 交叉注意力 | 解码器查询编码器输出 | Q 来自解码器，K/V 来自编码器 |

## 变体

| 模型 | 架构 | 代表 |
|------|------|------|
| Encoder-only | 仅编码器，做理解任务 | BERT、RoBERTa |
| Decoder-only | 仅解码器，做生成任务 | GPT 系列、Llama |
| Encoder-Decoder | 完整架构，做 seq2seq | T5、BART、原始 Transformer |

## 与相关概念的联系

- [[one-hour-function-to-transformer]]：本文的上游学习路径，第 06 集详细讲解
- [[attention-mechanism]]：Self-Attention 的数学基础与直觉
- [[neural-network-basics]]：函数与参数的基础知识
- [[ai-learning-path]]：完整 AI 学习路线

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
