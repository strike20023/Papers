---
link: https://arxiv.org/pdf/2508.02085
github: https://github.com/JARVIS-Xs/SE-Agent
note: 提出SE-Agent自进化框架，通过迭代优化推理轨迹在SWE-bench Verified上取得开源Agent最优表现（相对提升最高55%）
title: SE-Agent - Self-Evolution Trajectory Optimization in Multi-Step Reasoning with LLM-Based Agents
title_cn: SE-Agent - 基于LLM的多步推理自进化轨迹优化
tags:
  - paper
icon: LiNewspaper
---
## 摘要
LLM智能体在复杂推理与工具使用上展现了潜力，但其多步交互过程（问题求解的“轨迹”）往往未被充分利用。SE-Agent提出一种“自进化”框架，将过往试探性轨迹进行三步演化：修订（revision）、重组（recombination）与精炼（refinement），在多样化解空间中跳出局部最优，并通过跨轨迹启发提升推理质量。实验在 SWE-bench Verified 上，结合多种强LLM，带来最高达 55% 的相对提升，在开源Agent中达到最新最优表现。该方法强调利用历史交互反馈来迭代优化推理路径，减少冗余推理并提高任务完成率。
![](https://github.com/JARVIS-Xs/SE-Agent/raw/main/static/img/framework.jpg)
## 引言
使用SWE-agent作为baseline，在github issue任务上。
