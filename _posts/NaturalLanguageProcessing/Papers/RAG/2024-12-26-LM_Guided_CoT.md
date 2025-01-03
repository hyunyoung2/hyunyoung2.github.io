---
layout: post
title: Can Small Language Models Help Large Language Models Reason Better? - LM-Guided Chain-of-Thought
subtitle: CoT
category: Multi-modal
tags: [LLM, Rag]
permalink: /2024/12/26/LM_Guided_CoT/
css : /css/ForYouTubeByHyun.css
bigimg: 
  - "/img/Image/BigImages/carmel.jpg" : "Carmel-by-the-Sea, CA (2016)"
  - "/img/Image/BigImages/monterey.jpg" : "Monterey, CA (2016)"
  - "/img/Image/BigImages/stanford_dish.jpg" : "Stanford Dish, CA (2016)"
  - "/img/Image/BigImages/marian_beach_in_sanfran.jpg" : "MRINA of San Francisco, CA (2016)"
  - "/img/Image/BigImages/carmel2.jpg" : "Carmel-by-the-Sea, CA (2016)"
  - "/img/Image/BigImages/marina.jpg" : "MRINA of San Francisco, CA (2016)"
  - "/img/Image/BigImages/sanfrancisco.jpg" : "San Francisco, CA (2016)"
  
---

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [Can Samll Language Models Help Large Language Models Reason Better?: LM-Guided Chain-of-Thought (Lee et al., arXiv 2024)](https://arxiv.org/abs/2404.03414), that I read and studied. 

{% include MathJax.html %}


![Lee et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2024-12-26-LM_Guided_LM/LM_Guided_CoT_01.png)


For detailed experiment and explanation, refer to the paper, titled [Can Samll Language Models Help Large Language Models Reason Better?: LM-Guided Chain-of-Thought (Lee et al., arXiv 2024)](https://arxiv.org/abs/2404.03414)

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note(Abstract): </b>
We introduce a novel framework, LM-Guided CoT, that leverages a lightweight (i.e., <1B) language model (LM) for guiding a black-box large (i.e., >10B) LM in reasoning tasks. Specifically, the lightweight LM first generates a rationale for each input instance. The Frozen large LM is then prompted to predict a task output based on the rationale generated by the lightweight LM. Our approach is resource-efficient in the sense that it only requires training the lightweight LM. We optimize the model through 1) knowledge distillation and 2) reinforcement learning from rationale-oriented and task-oriented reward signals. We assess our method with multi-hop extractive question answering (QA) benchmarks, HotpotQA, and 2WikiMultiHopQA. Experimental results show that our approach outperforms all baselines regarding answer prediction accuracy. We also find that reinforcement learning helps the model to produce higher-quality rationales with improved QA performance.
</div>

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/2404.03414">The paper: Can Small Language Models Help Large Language Models Reason Better?" LM-Guided Chain-of-Thought(Lee et al., arXiv 2024)</a></div>

# Reference 

- Paper 
  - [ArXiv Version: Can Samll Language Models Help Large Language Models Reason Better?: LM-Guided Chain-of-Thought (Lee et al., arXiv 2024)](https://arxiv.org/abs/2404.03414)
  
- For Your Information
  - [Lil'Log's Gneralized Visual Language MOdels](https://lilianweng.github.io/posts/2022-06-09-vlm/)

- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

