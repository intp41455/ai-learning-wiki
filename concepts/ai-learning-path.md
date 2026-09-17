---
title: AI 学习路径
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [ai, learning, study-method, reference, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# AI 学习路径

> 基于闪客《一小时从函数到 Transformer》系列整理

## 推荐学习路径

### 第一阶段：数学直觉（第 01-03 集）
1. **函数思想**：相信世界可以用函数表示
2. **连接主义**：猜 + 简化，寻找近似解
3. **神经网络基础**：
   - 神经元 = 线性变换 + 激活函数
   - 前向传播：信号从左到右
   - 损失函数：衡量预测与真实的差距
   - 梯度下降：往损失减小的方向调整参数
   - 反向传播：链式法则逐层求导

### 第二阶段：经典架构（第 04-05 集）
4. **矩阵表示**：用矩阵运算简化神经网络公式
5. **CNN（卷积神经网络）**：
   - 卷积核 + 池化
   - 局部连接 + 权值共享
   - 适用于图像识别
6. **RNN（循环神经网络）**：
   - 隐藏状态在时间步之间传递
   - 词嵌入：One-Hot → 词向量
   - 梯度消失/爆炸问题
   - LSTM/GRU 门控机制

### 第三阶段：现代核心（第 06 集）
7. **Transformer 架构**：
   - Self-Attention：Q/K/V 三分法
   - 位置编码：正弦/余弦函数
   - Multi-Head Attention：多头并行
   - Encoder-Decoder：编码器 + 解码器
   - Masked Attention：掩码机制

### 第四阶段：大模型时代（第 07 集）
8. **LLM 核心概念**：
   - Token、Embedding、Context Window
   - Temperature、Top-p/k
   - Fine-tuning、RLHF
   - RAG、Agent
   - 涌现、AGI、多模态

## 学习资源

| 资源 | 类型 | 说明 |
|------|------|------|
| 【闪客】一小时从函数到 Transformer | 视频系列 | 7集，总时长约1小时，大白话讲解 |
| Attention Is All You Need | 论文 | Transformer 原始论文，看完视频后看会很容易理解 |
| 自然搞懂深度学习（基于Pytorch架构） | 博客笔记 | 参考闪客系列写的详细笔记，含 Think-Help |
| 3Blue1Brown 神经网络课 | 视频 | 中文配音版，动画讲解 |
| 吴恩达深度学习 | 课程 | Coursera 经典课程 |

## 与相关概念的联系

- [[one-hour-function-to-transformer]] — 本路径的核心视频资源
- [[neural-network-basics]] — 第一阶段基础
- [[cnn-architecture]] — 第二阶段经典架构
- [[rnn-architecture]] — 第二阶段序列模型
- [[transformer-architecture]] — 第三阶段现代核心
- [[llm-terms-100]] — 第四阶段大模型术语
- [[attention-mechanism]] — Transformer 的核心机制

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
