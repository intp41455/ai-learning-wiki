---
title: LLM 核心术语 100 词
created: 2026-09-03
updated: 2026-09-03
type: concept
tags: [llm, terminology, learning, concept]
sources: [raw/transcripts/flash-client-one-hour-function-to-transformer.md]
confidence: high
---

# LLM 核心术语 100 词

> 基于闪客《一小时从函数到 Transformer》第 07 集详细复刻

## 核心术语速览

| 术语 | 含义 | 闪客讲解要点 |
|------|------|-------------|
| Token | 文本最小处理单元 | 不一定是完整词，可能是词片段 |
| Embedding | 词 → 向量 | 语义相近的词，向量距离也近 |
| Context Window | 模型一次处理的最大长度 | 类似人的短期记忆容量 |
| Temperature | 生成时的随机性控制 | 高 = 更有创意，低 = 更确定 |
| Top-p / Top-k | 采样策略 | 控制生成多样性 |
| Fine-tuning | 微调 | 在预训练基础上继续训练特定任务 |
| RLHF | 人类反馈强化学习 | 让模型输出更符合人类偏好 |
| Prompt Engineering | 提示词工程 | 通过 prompt 引导模型输出 |
| RAG | 检索增强生成 | 先检索相关知识，再生成回答 |
| Agent | 自主智能体 | 能规划、使用工具、执行任务 |

## 与相关概念的联系

- [[one-hour-function-to-transformer]]：第 07 集完整讲解
- [[transformer-architecture]]：LLM 的底层架构
- [[ai-learning-path]]：完整 AI 学习路线

## 可视化

- 思维导图 → [[ai-mindmap]]
- 知识图谱 → [[ai-knowledge-graph]]
