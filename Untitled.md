你提到“从与用户的对话交互中获得知识来增强对话”——也就是：在对话过程中实时／动态地从用户输入、交互历史中学习、积累知识，然后利用这些知识提升后续对话质量。以下我整理了相关的大模型／对话系统研究方向 + 代表性论文，供你参考。若你想我可以帮你查找**专门研究“在线交互-学习”（online interactive learning）**的论文。

⸻

✅ 研究方向概览

这个主题大致可拆为几个子问题：
	1.	对话系统如何捕捉用户输入中新的知识（例如用户提供的偏好、事实、背景）并记忆下来。
	2.	如何将这些知识整合进模型的对话生成或理解流程，使得下文对话更契合用户。
	3.	在线学习／交互学习（interactive learning）：模型不仅被预训练或离线微调，而是在与用户长期交互中持续更新、演化。
	4.	对话评价与知识利用：模型怎样评估“用了用户信息后生成的回答是否更好”？以及如何防止误用用户输入（隐私、错误信息）？
	5.	对话历史与上下文感知：如何基于多轮历史、环境、用户特征形成更精准的回应。

⸻

📚 代表性论文

下面是一些与你关心题目较为贴近的论文，带上摘要／关键点，供你深入读。
	•	DialoGPT: Large‑Scale Generative Pre‑training for Conversational Response Generation (Zhang et al., 2019)
这篇是一个较早将大规模预训练语言模型用于开放域对话生成的工作，训练于 Reddit 对话数据上。 ￼
虽然它不是专门做“从用户交互中学习知识”这一点，但作为对话生成模型的基础技术参考，非常有价值。
	•	EVA: An Open‑Domain Chinese Dialogue System with Large‑Scale Generative Pre‑Training (Zhou et al., 2021)
在中文开放域对话中规模较大的一项工作，构建了 2.8 B 参数模型、1.4 B 条上下文-响应对话数据。 ￼
同样，这论文主要是预训练与生成，不完全是交互学习，但可作为“从大规模对话数据中学习”的参考。
	•	Dialogue Response Selection with Hierarchical Curriculum Learning (Su et al., ACL 2021)
针对对话系统中的“响应选择”任务，提出了分层课程学习（easy→hard）的方法。 ￼
虽然聚焦于响应选择而非知识记忆，但为“逐步增强模型能力”的思路提供借鉴。
	•	Learning from Interaction (Brantley et al., 2025)
这篇比较直接触及“从交互中学习”的概念。提到 foundation 模型 + 交互 (dialogue) 的学习机制。 ￼
虽然可能还比较概念化，但值得深入了解。
	•	DEMO: Reframing Dialogue Interaction with Fine‑grained Element Modeling (Wang et al., 2024)
提出了 “Dialogue Element Modeling” 的任务，包括对话生命周期（前奏、交谈、收尾）和细粒度元素建模。 ￼
虽然还不是专门“知识积累”的，但对“增强对话理解”的方向很有帮助。

⸻

🎯 与 “从用户交互中学习知识” 这一主题特别匹配的补充视角
	•	知识记忆／用户模型：当用户在对话中透露偏好、背景、历史信息，模型如何记住并利用这些？这要求有用户状态建模和长期记忆机制。
	•	在线微调 / 增量学习：传统对话系统通常在训练阶段固定模型，交互时不变。要“学习”，则可能需要在线更新、或至少在后台收集交互数据用于定期微调。
	•	交互反馈机制：模型可能从用户反应（纠正／评价／继续追问）中学习。这涉及强化学习、自我监督、用户反馈循环。
	•	知识获取与校验：用户可能提供错误或偏见信息。模型如何识别、校验、整合这些用户知识？
	•	评价机制：当模型使用用户交互中获得的知识，如何评估其效果？自动指标＋人类评价都重要。
	•	隐私与伦理：从用户获取知识也伴随隐私风险。如用户提供敏感信息，系统如何安全／合规地记忆与使用。

⸻

🔍 建议你重点阅读/检索的几个关键词

为了查找更多“从交互学习”的论文，可以用以下关键词组合检索：
	•	“interactive dialogue learning from user interaction”
	•	“online learning dialogue system user feedback”
	•	“user modeling in conversational agents long‐term memory”
	•	“dialogue system knowledge accumulation from interactions”
	•	“incremental learning large language model dialogue memory”

⸻

如果你愿意，我可以帮你检索 5 – 10 篇专门聚焦“对话系统从交互学习知识”的最新论文（2023-2025年），并为每篇做摘要。你看要不要？