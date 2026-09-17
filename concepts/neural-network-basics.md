---
title: 神经网络基础
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [neural-network, deep-learning, learning, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# 神经网络基础

> 基于闪客《一小时从函数到 Transformer》第 01-03 集详细复刻

## 函数：最基础的黑盒子
- 输入 x → 经过某种变换 → 输出 y
- 神经网络本质：一个超级复杂的复合函数
- y = g(w₁x₁ + w₂x₂ + ... + b)
  - g = 激活函数（非线性）
  - w = 权重（可学习参数）
  - b = 偏置（可学习参数）

## 什么是神经网络
- 由大量"神经元"组成的网络
- 每个神经元接收输入 → 加权求和 → 加偏置 → 经过激活函数 → 输出
- 闪客比喻：像大脑的神经元，但简化了无数倍

### 激活函数
- 没有激活函数：多层网络等价于单层线性变换
- 非线性激活让网络能拟合任意复杂函数
- 常见激活函数：
  - Sigmoid：输出 0-1，早期用得多，现在少用
  - Tanh：输出 -1 到 1，比 Sigmoid 好一点
  - ReLU：输出 max(0, x)，最常用，简单高效

## 前向传播
- 数据从输入层 → 隐藏层 → 输出层的完整计算过程
- 每层：Z = W·X + b → A = g(Z)
- 矩阵运算大幅加速计算
- 权重矩阵 W 的形状 = (输出维度, 输入维度)
- 参数量 = 输入维度 × 输出维度 + 偏置

## 损失函数（Loss Function）
- 衡量模型预测与真实值的差距
- 目标：找到最优参数使损失最小
- 常见损失：
  - MSE（均方误差）：回归任务
  - 交叉熵（Cross Entropy）：分类任务

## 梯度下降
- 思路：沿损失函数梯度方向更新参数
- w = w - η · ∇L(w)
- η = 学习率（步长大小）
- 直观理解：下山，每一步往最陡的方向走

### 学习率
- 太大：损失震荡，不收敛
- 太小：收敛极慢
- 常用策略：学习率衰减、Adam 自适应学习率

## 反向传播（Backpropagation）
- 链式法则的高效实现
- 从输出层往输入层逐层计算梯度
- 让深度网络的训练成为可能
- dL/dw = dL/da · da/dz · dz/dw

## 优化器（Optimizer）
- SGD：最基础，纯梯度下降
- Momentum：加惯性，冲出局部最优
- Adam：自适应学习率 + 动量，最常用

## Batch 与 Epoch
- Batch：一次参数更新的样本数
- Epoch：完整遍历一次训练集
- Batch size 影响：内存占用、梯度稳定性、收敛速度

## 过拟合 vs 欠拟合
- 欠拟合：模型太简单，训练集上表现就差
- 过拟合：模型太复杂，训练集表现好，测试集差
- 过拟合解决：Dropout、L2 正则、数据增强、早停
- 欠拟合解决：增加模型容量、减少正则、训练更久

## 数据集划分
- 训练集：学习参数
- 验证集：调超参、选模型
- 测试集：最终评估，一次都不许碰

## 与相关概念的联系

- [[one-hour-function-to-transformer]]：第 01-03 集的完整讲解
- [[transformer-architecture]]：神经网络是 Transformer 的前置知识
- [[attention-mechanism]]：Self-Attention 建立在神经网络基础之上
- [[ai-learning-path]]：完整 AI 学习路线

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
