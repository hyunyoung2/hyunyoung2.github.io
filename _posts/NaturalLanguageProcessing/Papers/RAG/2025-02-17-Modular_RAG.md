---
layout: post
title: Modular RAG - Transforming RAG Systems into LEGO-like Reconfigurable Frameworks
subtitle: Modular-RAG
category: RAG
tags: [LLM, RAG]
permalink: /2025/02/17/Modular_RAG/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [Modular RAG: Transforming RAG Systems into LEGO-like Reconfiguragble Frameworks (Gao et al. arXiv 2024)](https://arxiv.org/abs/2407.21059), that I read and studied. 

{% include MathJax.html %}

The following indicates the Naive RAG and Advaced RAG Scenario.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_01.png)

The following indicates the Modular RAG Scenario.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_02.png)

The following indicates the three paradigms of RAG system.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_03.png)

The following two images denote tha linear pattern of RAG System.

i.e. The below image is Sequential.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_04.png)

i.e The below image is Rewrite-Retrieval-Read (RRR). 

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_05.png)

The following indicates the conditional pattern of RAG system.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_06.png)

The following three images indicate the branching pattern of RAG system.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_07.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_08.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_09.png)

The following five images indicate the loop pattern of RAG system.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_10.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_11.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_12.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_13.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_14.png)

The following images is tuning pattern of RAG System.

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_15.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_16.png)

![Gao et al. arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/RAG/2025-03-08-Modular_RAG/Modular_RAG_17.png)

For detailed experiment and explanation, refer to the paper, titled [Modular RAG: Transforming RAG Systems into LEGO-like Reconfiguragble Frameworks (Gao et al. arXiv 2024)](https://arxiv.org/abs/2407.21059)

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note(Abstract): </b>
Retrieval-augmented Generation (RAG) has markedly enhanced the capabilities of Large Language Models (LLMs) in tackling knowledge-intensive tasks. The increasing demands of application scenarios have driven the evolution of RAG, leading to the integration of advanced retrievers, LLMs and other complementary technologies, which in turn has amplified the intricacy of RAG systems. However, the rapid advancements are outpacing the foundational RAG paradigm, with many methods struggling to be unified under the process of "retrieve-then-generate". In this context, this paper examines the limitations of the existing RAG paradigm and introduces the modular RAG framework. By decomposing complex RAG systems into independent modules and specialized operators, it facilitates a highly reconfigurable framework. Modular RAG transcends the traditional linear architecture, embracing a more advanced design that integrates routing, scheduling, and fusion mechanisms. Drawing on extensive research, this paper further identifies prevalent RAG patterns-linear, conditional, branching, and looping-and offers a comprehensive analysis of their respective implementation nuances. Modular RAG presents innovative opportunities for the conceptualization and deployment of RAG systems. Finally, the paper explores the potential emergence of new operators and paradigms, establishing a solid theoretical foundation and a practical roadmap for the continued evolution and practical deployment of RAG technologies.
</div>

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/2407.21059">The paper: Modular RAG: Transforming RAG Systems into LEGO-like Reconfigurable Frameworks (Gao et al., arXiv 2024)</a></div>

# Reference 

- Paper 
  - [arXiv Version: Modular RAG: Transforming RAG Systems into LEGO-like Reconfiguragble Frameworks (Gao et al. arXiv 2024)](https://arxiv.org/abs/2407.21059)
 
- For Your Information
  - [Retrieval Augmented Generation-LLM Comparison](https://orkg.org/comparison/R716040)
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

