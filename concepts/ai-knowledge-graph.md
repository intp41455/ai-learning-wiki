---
title: AI 知识体系 — 知识图谱
created: 2026-09-06
updated: 2026-09-06
type: graph
tags: [ai, machine-learning, deep-learning, llm, summary]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
related: [ai-learning-path, neural-network-basics, cnn-architecture, rnn-architecture, transformer-architecture, attention-mechanism, llm-terms-100, one-hour-function-to-transformer]
---

# AI 知识体系 — 知识图谱

> 来源：闪客《一小时从函数到 Transformer》（B站 BV1NCgVzoEG9）
> 返回总览：[[ai-learning-path]]

```mermaid
%%{init: {"theme": "base", "themeVariables": {"fontFamily": "-apple-system, Segoe UI, PingFang SC, Microsoft YaHei, sans-serif", "fontSize": "14px", "lineColor": "#9aa6b2", "primaryBorderColor": "#cfd6df", "primaryColor": "#fafbfc", "primaryTextColor": "#1f2329"}, "themeCSS": ".node rect,.node polygon,.node ellipse{stroke:#cfd6df !important;stroke-width:1.2px !important}.edge path{stroke:#9aa6b2 !important;stroke-width:1.4px !important}.edgeMarker{stroke:#9aa6b2 !important;fill:#9aa6b2 !important}.edgeLabel{background-color:#ffffff !important;font-size:12px !important;color:#5a6470 !important;padding:2px 6px !important;border-radius:4px !important;border:1px solid #e4e8ee !important}.label,.nodeLabel{font-family:-apple-system,Segoe UI,PingFang SC,Microsoft YaHei,sans-serif !important}.cluster rect{stroke:#dde3ea !important;stroke-width:1px !important;fill:#fafbfc !important}.note rect,.note polygon{stroke:#d8dde3 !important;stroke-width:1px !important;fill:#fafbfc !important}"}}%%
graph TD
    F[函数思想<br/>世界可用函数表示] --> NN[神经网络]
    NN --> P[参数]
    NN --> L[损失函数]
    NN --> GD[梯度下降]
    NN --> BP[反向传播]
    L --> GD
    BP --> GD
    GD --> OPT[优化器]

    NN --> M[矩阵表示]
    M --> CNN[CNN 卷积神经网络]
    M --> RNN[RNN 循环神经网络]

    CNN --> C1[卷积核 + 特征图]
    CNN --> C2[池化]
    CNN --> C3[局部连接 + 权值共享]

    RNN --> R1[隐藏状态传递]
    RNN --> R2[词嵌入 One-Hot 到词向量]
    RNN --> R3[梯度消失/爆炸]
    R3 --> LSTM[LSTM / GRU 门控]

    RNN --> T[Transformer]
    C3 --> T
    T --> T1[自注意力 Self-Attention]
    T --> T2[多头注意力 Multi-Head]
    T --> T3[位置编码 Positional Encoding]
    T --> T4[编码器-解码器结构]
    T1 --> QKV[Q / K / V]
    QKV --> SA[缩放点积注意力]

    T --> LLM[大语言模型]
    LLM --> L1[Token / Embedding]
    LLM --> L2[Temperature 采样]
    LLM --> L3[RLHF 对齐]
    LLM --> L4[RAG 检索增强]
    LLM --> L5[Agent]

    R2 --> L1
    SA --> T1
```

## 关联笔记

- [[ai-learning-path]] — 学习路径总览
- [[neural-network-basics]] — 函数、参数、损失、梯度下降、反向传播
- [[cnn-architecture]] — 卷积核、池化、权值共享
- [[rnn-architecture]] — 词嵌入、LSTM/GRU、梯度消失
- [[transformer-architecture]] — 编码器-解码器、位置编码、多头注意力
- [[attention-mechanism]] — Q/K/V、缩放点积、掩码注意力
- [[llm-terms-100]] — 大模型 100 个术语
- [[one-hour-function-to-transformer]] — 原始讲稿复刻
