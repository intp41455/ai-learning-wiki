---
title: AI 知识体系 — 思维导图
created: 2026-09-06
updated: 2026-09-06
type: mindmap
tags: [ai, machine-learning, deep-learning, llm, summary]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
related: [ai-learning-path, ai-knowledge-graph, one-hour-function-to-transformer]
---

# AI 知识体系 — 思维导图

> 返回总览：[[ai-learning-path]] ｜ 图谱版：[[ai-knowledge-graph]]

```mermaid
%%{init: {"theme": "base", "themeVariables": {"primaryColor": "#fafbfc", "primaryTextColor": "#2b3340", "primaryBorderColor": "#cfd6df", "lineColor": "#a8b3bf", "fontFamily": "-apple-system, Segoe UI, PingFang SC, Microsoft YaHei, sans-serif", "fontSize": "13px"}, "themeCSS": ".mindmap-node .background{fill:#ffffff !important;stroke:#cfd6df !important;stroke-width:1px !important}.mindmap-node.section-0 .background{fill:#eef4fb !important;stroke:#b6cad9 !important}.mindmap-node.section-2 .background{fill:#fafbfc !important}.edge{fill:none !important;stroke:#a8b3bf !important;stroke-width:1.3px !important}.edge.section-edge-0{stroke:#7a8a99 !important;stroke-width:1.6px !important}.text-inner-tspan,.text-outer-tspan{fill:#2b3340 !important;font-weight:500 !important}.mindmap-node{padding:6px}"}}%%
mindmap
  root((从函数到<br/>Transformer))
    函数思想
      相信世界可以用函数表示
      连接主义：猜加简化
    神经网络基础
      神经元 = 线性变换加激活
      前向传播：信号从左到右
      损失函数：衡量差距
      梯度下降：沿损失减小方向
      反向传播：链式法则逐层求导
      优化器
    矩阵表示
      用矩阵简化神经网络公式
    CNN
      卷积核 + 特征图
      池化
      局部连接 + 权值共享
      适用于图像
    RNN
      隐藏状态时间步传递
      词嵌入：One-Hot 到词向量
      梯度消失/爆炸
      LSTM / GRU 门控
    Transformer
      自注意力 Self-Attention
      Q / K / V
      缩放点积
      多头注意力
      位置编码
      编码器-解码器
      并行计算优于 RNN
    大模型 100 词
      Token
      Embedding
      Temperature
      RLHF
      RAG
      Agent
```

## 关联笔记

- [[ai-learning-path]] — 分阶段学习路径
- [[ai-knowledge-graph]] — 同一内容的知识图谱版本
- [[one-hour-function-to-transformer]] — 完整讲稿
- [[neural-network-basics]] / [[cnn-architecture]] / [[rnn-architecture]] / [[transformer-architecture]] / [[attention-mechanism]] / [[llm-terms-100]]
