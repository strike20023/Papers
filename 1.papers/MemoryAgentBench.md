---
link: https://arxiv.org/pdf/2507.05257
github: https://github.com/HUST-AI-HYZ/MemoryAgentBench
note: ""
title: Evaluating Memory in LLM Agents via Incre-mental Multi-Turn Interactions
title_cn: 通过增量多轮交互评估LLM代理的内存
tags:
  - paper
icon: LiNewspaper
---

## 摘要
本文提出 MemoryAgentBench，用于系统性评估具备记忆机制的 LLM 代理（Memory Agents）的四项核心能力：精准检索（Accurate Retrieval）、测试时学习（Test-Time Learning）、长程理解（Long-Range Understanding）与选择性遗忘（Selective Forgetting）。与以往依赖静态长上下文或单回合设置的基准不同，MemoryAgentBench 将现有长上下文数据集及新构建数据转化为多轮、增量式交互格式，模拟代理在运行时持续“注入信息—更新记忆—跨轮次检索”的真实工作流。作者评测了从简单上下文/检索增强（RAG）到带外部记忆模块与工具集成的多类代理，结果显示当前方法无法同时掌握四项能力，凸显了对更全面记忆机制的研究需求。[1][2]

## 引言
动机：现有代理评测多集中于推理、规划与执行，记忆（如何存储、更新、检索长程信息）却缺乏统一、真实交互场景下的系统评测。记忆代理不仅需要“记住”，还要能在运行中学习新知识、跨超长序列整合信息，并在出现矛盾或过时信息时进行选择性遗忘。

核心贡献：
- 提出四项能力维度，覆盖记忆的“取、学、融、忘”。
- 将数据改造成增量多轮格式，贴近真实交互过程而非一次性长上下文。
- 统一评测协议，覆盖多类记忆代理架构（上下文、RAG、外部记忆、工具集成）。
- 实证发现：现有方法在四项能力上普遍存在短板，需面向综合记忆机制进一步研究。

备注：论文不同版本中第四项能力表述为“选择性遗忘”或“冲突消解（Conflict Resolution）”，最新摘要采用“选择性遗忘”。[1][4]

## 任务与数据
- 能力维度与任务设计：
  - 精准检索（AR）：面向一跳/多跳检索，能在一次查询下取回正确片段。
  - 测试时学习（TTL）：在部署期以交互注入新知识/技能，立刻体现在后续回复中。
  - 长程理解（LRU）：跨超长上下文（≥100k tokens）整合分布式信息，回答全局性问题。
  - 选择性遗忘（SF）：当出现矛盾或过时信息时，及时修订/覆盖/移除已存信息。
- 数据来源与处理：整合既有长上下文基准并进行多轮改写，同时新构建数据以覆盖能力空缺；采用“一次注入、对应多问”的设计以提高评测效率。仓库说明提到新增的 EventQA 与 FactConsolidation 两个数据集。[2]

## 评测协议
- 多轮增量交互：逐步注入信息，跨轮次追问；要求代理显式或隐式管理其外部/内部记忆。
- 指标与判分：以准确率等客观指标为主；部分长程理解/摘要类任务使用大模型判分辅助（仓库示例采用如 gpt-4o 的判分脚本）。[2]
- 统一设置：在不同代理架构与数据上保持一致的流程与采样，保证可比性。

## 基线与方法
- 评测对象涵盖：
  - 仅依赖上下文窗口的长上下文代理；
  - 检索增强（RAG）系统（含多种索引/重排/分块策略）；
  - 带外部记忆模块的代理（向量库/数据库/记忆工具）；
  - 集成工具链的复杂代理。

## 主要发现
- 没有单一方法在四项能力上全面领先：不同架构存在明显强项与弱项。
- 测试时学习与选择性遗忘存在张力：快速吸收新知识同时需可靠“忘掉”旧或冲突信息。
- 长程理解仍具挑战：超长序列上的全局整合能力不足，易受检索/分块/摘要质量影响。
- RAG 管线与分块粒度对性能敏感：仓库提供了分块大小的消融脚本，提示数据切分策略重要性。[2]

## 局限与讨论
- 评测部分依赖大模型判分，存在一致性与成本问题；未来可引入更可重复的自动指标。
- 数据虽覆盖多维能力，但真实应用中的多模态记忆、参数级记忆等仍未完全纳入。
- 代理的记忆形态多样（参数、向量、文本、外部数据库），统一评测仍需不断迭代。

## 复现与资源
- 代码仓库：`https://github.com/HUST-AI-HYZ/MemoryAgentBench`。[2]
- 数据集（HuggingFace）：`https://huggingface.co/datasets/ai-hyz/MemoryAgentBench`。[2]
- 评测脚本示例：长程问答与摘要的 LLM 判分脚本位于仓库 `llm_based_eval` 目录。[2]

## 引用
```
@article{hu2025evaluating,
  title={Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions},
  author={Hu, Yuanzhe and Wang, Yu and McAuley, Julian},
  journal={arXiv preprint arXiv:2507.05257},
  year={2025}
}
```

## 参考
- [1] arXiv 摘要页：`https://arxiv.org/abs/2507.05257`
- [2] GitHub 仓库：`https://github.com/HUST-AI-HYZ/MemoryAgentBench`
- [3] HuggingFace Papers 页：`https://huggingface.co/papers/2507.05257`
- [4] arXiv HTML（v1）页：`https://arxiv.org/html/2507.05257v1`
