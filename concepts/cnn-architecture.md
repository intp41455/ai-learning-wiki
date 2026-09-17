---
title: CNN 架构
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [cnn, convolution, deep-learning, computer-vision, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# CNN 架构

> 基于闪客《一小时从函数到 Transformer》第 04 集详细复刻

## 为什么需要 CNN
- 全连接网络处理图像：参数量爆炸
- 28×28 图像 → 784 维输入 → 隐藏层 128 神经元 → 参数量 100K+
- 大图像 224×224 → 全连接层参数量可达上亿
- 闪客比喻：用全连接处理图像就像用大炮打蚊子

## 卷积核（Kernel / Filter）
- 一个小矩阵，在图像上滑动
- 每次滑动做点积运算 → 特征图（Feature Map）
- 参数量共享：同一个卷积核用在整个图像上

### 卷积的直觉
- 类比：用一个"模板"在图像上找模式
- 边缘检测核、模糊核、锐化核
- 深度学习中：卷积核自动学习

## 池化（Pooling）
- Max Pooling：取区域最大值
- Average Pooling：取区域平均值
- 作用：降维、平移不变性、减少计算量

## CNN 整体结构
- 卷积层 → 激活函数 → 池化层 → 重复 → 全连接层 → 输出
- 经典架构演进：LeNet → AlexNet → VGG → ResNet

## 局部连接与权值共享
- 局部连接：每个神经元只看输入的一个小区域
- 权值共享：同一卷积核扫过整个图像
- 参数量从 O(n²) 降到 O(k²)

## 与相关概念的联系

- [[one-hour-function-to-transformer]]：第 04 集完整讲解
- [[neural-network-basics]]：CNN 建立在全连接网络基础之上
- [[transformer-architecture]]：CNN 之后引出 RNN，再到 Transformer
- [[ai-learning-path]]：完整 AI 学习路线

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
