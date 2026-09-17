---
title: RNN 架构
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [rnn, recurrent, sequence, deep-learning, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# RNN 架构

> 基于闪客《一小时从函数到 Transformer》第 05 集详细复刻

## 词嵌入（Word Embedding）
- 把词从离散的 ID 变成连续的向量
- Word2Vec：skip-gram / CBOW
- 核心直觉：语义相近的词，向量距离也近
- 经典例子：king - man + woman ≈ queen

## 序列数据的挑战
- 图像：固定尺寸，可以整张输入
- 文本：长度可变，词序重要
- 需要一个能处理"序列"的模型

## RNN（循环神经网络）
- 核心思想：带"记忆"的神经网络
- 每个时间步：h_t = f(h_{t-1}, x_t)
- 同一网络参数在不同时间步复用

## RNN 的问题：梯度消失/爆炸
- 反向传播要穿过整个时间链
- 链式法则连乘 → 梯度指数衰减/爆炸
- 长距离依赖学不到（第 1 个词对第 100 个词的影响几乎为 0）

## LSTM / GRU
- 门控机制：输入门、遗忘门、输出门
- 选择性记忆：遗忘门决定丢弃什么，输入门决定记住什么
- 缓解梯度消失，但仍有顺序依赖

## 从 RNN 到 Transformer 的必然性
- RNN 系列：顺序处理，无法并行
- Transformer：全局注意力，完全并行
- 大数据时代，计算效率决定上限

## 与相关概念的联系

- [[one-hour-function-to-transformer]]：第 05 集完整讲解
- [[transformer-architecture]]：RNN 之后引出 Transformer
- [[attention-mechanism]]：Transformer 用 Self-Attention 替代了 RNN 的循环
- [[neural-network-basics]]：RNN 建立在全连接网络基础之上
- [[ai-learning-path]]：完整 AI 学习路线

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
