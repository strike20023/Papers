---
link: https://arxiv.org/pdf/1810.00278
github:
note: 发布MultiWOZ，一个跨域、全标注的Wizard-of-Oz任务型对话数据集（约1万对话，含belief state与dialogue act标签），为端到端对话与状态追踪研究提供基准；论文被EMNLP 2018接收。
title: MultiWOZ - A Large-Scale Multi-Domain Wizard-of-Oz Dataset for Task-Oriented Dialogue Modelling
title_cn: MultiWOZ：大规模多领域Wizard-of-Oz任务型对话数据集
tags:
  - paper
icon: LiNewspaper
---

## 摘要
对话研究的突破长期受限于数据规模与标注质量。MultiWOZ 提供了一个跨多个领域的大规模、全标注任务型对话数据集（约 10k 人工撰写的多轮人-人对话），并开源了包含对话状态（belief state）与对话行为（dialogue act）在内的完整标注。作者详细描述了众包数据收集流程、数据结构与分析，并报告了若干基线任务的结果（状态追踪、对话行为识别、响应生成），为后续研究提供了可复现实验与对比参考。

## 引言
MultiWOZ 的目标是为任务型对话系统提供一个多领域、规模化且高质量标注的数据基准，涵盖餐馆、酒店、景点、出租车等多个业务领域。数据采用 Wizard-of-Oz 众包流程，以人类编写的真实对话模拟用户与系统交互，从而更贴近真实需求与语言现象。

## 数据与标注
- 规模：约 10,000 条多轮人-人对话，至少比此前同类数据集大一个数量级；
- 领域：多域覆盖（餐馆、酒店、景点、出租车等），支持跨域对话；
- 标注：
  - Belief State（用户目标/槽位），用于对话状态追踪；
  - Dialogue Acts（系统动作），用于策略学习与行为识别；
  - 文本响应（系统回复），用于生成任务；
- 采集方式：完全基于众包，无需专业标注员；
- 数据质量：提供结构化解析与统计分析，并给出若干基线任务表现。

## 基准与结果
- 任务：对话状态追踪（DST）、对话行为识别（DA）、响应生成（NLG）等；
- 结果：报告了多项基线模型的性能，展示数据的可用性并为后续工作提供基准参考。

