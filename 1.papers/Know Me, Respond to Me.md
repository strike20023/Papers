---
link: https://arxiv.org/pdf/2504.14225
github: https://github.com/bowen-upenn/PersonaMem
note: 发表在COLM 2025
title: Know Me, Respond to Me - Benchmarking LLMs for Dynamic User Profiling and Personalized Responses at Scale
title_cn: 知道我，回复我 - 基准测试大型语言模型在动态用户画像和个性化响应中的应用
tags:
  - paper
icon: LiNewspaper
---
## 摘要
Large Language Models (LLMs) have emerged as personalized assistants for users across a wide range of tasks – from offering writing support to delivering tailored recommendations or consultations. Over time, the interaction history between a user and an LLM can provide extensive information about an individual’s traits and preferences. However, open questions remain on how well LLMs today can effectively leverage such history to 
>大型语言模型（LLMs）已成为用户在广泛任务中的个性化助手——从提供写作支持到提供定制推荐或咨询。随着时间的推移，用户与LLM之间的交互历史可以提供关于个人特性和偏好的大量信息。然而，关于今天的LLM如何有效地利用这种历史来

(1) internalize the user’s inherent traits and preferences, 
(2) track how the user profiling and preferences evolve over time, and 
(3) generate personalized responses accordingly in new scenarios.  
>（1）内化用户的固有特性和偏好，（2）跟踪用户画像和偏好随时间的变化，以及（3）根据新场景生成相应的个性化响应，仍存在开放性问题。

In this work, we introduce the PERSONAMEM benchmark. PERSONAMEM features curated user profiles with over 180 simulated user-LLM interaction histories, each containing up to 60 sessions of multi-turn conversations across 15 real-world tasks that require personalization. Given an in-situ user query, i.e. query issued by the user from the first-person perspective, we evaluate LLM chatbots’ ability to identify the most suitable response according to the current state of the user’s profile. We observe that current LLMs still struggle to recognize the dynamic evolution in users’ profiles over time through direct prompting approaches. As a consequence, LLMs often fail to deliver responses that align with users’ current situations and preferences, with frontier models such as GPT-4.1, o4-mini, GPT-4.5, o1, or Gemini-2.0 achieving only around 50% overall accuracy, suggesting room for improvement. We hope that PERSONAMEM, along with the user profile and conversation simulation pipeline, can facilitate future research in the development of truly user-aware chatbots. Code and data are available at github.com/bowen-upenn/PersonaMem.
>在这项工作中，我们介绍了PERSONAMEM基准。PERSONAMEM具有经过精心挑选的用户画像，包含超过180个模拟的用户-LLM交互历史，每个历史包含多达60个会话的多轮对话，涉及15个需要个性化的真实世界任务。给定一个现场用户查询，即用户从第一人称视角发出的查询，我们评估LLM聊天机器人在根据用户当前画像状态识别最合适响应的能力。我们观察到，当前的LLM仍然难以通过直接提示方法识别用户画像随时间的动态演变。因此，LLM往往无法提供与用户当前情况和偏好相符的响应，前沿模型如GPT-4.1、o4-mini、GPT-4.5、o1或Gemini-2.0的整体准确率仅约为50%，这表明仍有改进空间。我们希望PERSONAMEM，连同用户画像和对话模拟管道，可以促进真正用户感知聊天机器人的未来发展研究。
## 引言
Personalization in LLMs involves adapting model responses to specific traits, preferences, and historical interactions of each user, moving beyond generic responses to more relevant and tailored ones. Since different users have different personas, it becomes an emergent need for LLMs to be pluralistic—capable of adapting to different user characteristics across different scenarios, thereby enhancing user experience and engagement.
![](https://arxiv.org/html/2504.14225v2/x1.png)
For example, as illustrated in Figure 1, a user initially said, ”I like pizza”, but mentioned in a later session, ”I’ve started exploring gluten-free options,” upon discovering a gluten allergy. When the user again asks for food recommendations, a personalized LLM chatbot should be able to track the change, and provide recommendations according to the user’s current situation. Current LLM chatbots often fail to recognize and adapt to evolving user personas. This may lead users to perceive these chatbots as less helpful and empathetic, ultimately diminishing satisfaction.
>例如，如图1所示，用户最初说，“我喜欢披萨”，但在后来的会话中提到，“我发现对麸质过敏后，我开始探索无麸质选项。”当用户再次请求食物推荐时，一个个性化的LLM聊天机器人应该能够跟踪这种变化，并根据用户的当前情况提供推荐。当前的LLM聊天机器人往往无法识别和适应不断变化的用户角色。这可能导致用户认为这些聊天机器人不那么有帮助和有同理心，最终降低满意度。

## 实验
![[Pasted image 20251103150926.png]]
7中任务类型，使用4个候选项。

![[Pasted image 20251103151133.png]]

Models fall short on generating new ideas or providing suggestions in new scenarios.
As shown in Figure 3, tasks such as **”Suggest New Ideas”, ”Provide Preference-Aligned Recommendations”, and ”Generalize Reasons to New Scenarios”** yield the lowest performance
across all models, highlighting the challenge of generating personalized responses in novel
contexts—particularly when identifying new facts.

