---
layout: post
title: Active Retrieval Augmented Generation
subtitle: Active RAG
category: Rag
tags: [LLM, Rag]
permalink: /2024/12/26/Active_RAG/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [Active Retrieval Augmented Generation (Jiang et al., arXiv 2023)](https://arxiv.org/abs/2305.06983), that I read and studied. 

{% include MathJax.html %}


![Jiang et al. arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/RAG/2024-12-26-Active_RAG/Active_RAG_01.png)


For detailed experiment and explanation, refer to the paper, titled [Active Retrieval Augmented Generation (Jiang et al., arXiv 2023)](https://arxiv.org/abs/2305.06983)

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note(Abstract): </b>
Despite the remarkable ability of large language models (LMs) to comprehend and generate language, they have a tendency to hallucinate and create factually inaccurate output. Augmenting LMs by retrieving information from external knowledge resources is one promising solution. Most existing retrieval augmented LMs employ a retrieve-and-generate setup that only retrieves information once based on the input. This is limiting, however, in more general scenarios involving generation of long texts, where continually gathering information throughout generation is essential. In this work, we provide a generalized view of active retrieval augmented generation, methods that actively decide when and what to retrieve across the course of the generation. We propose Forward-Looking Active REtrieval augmented generation (FLARE), a generic method which iteratively uses a prediction of the upcoming sentence to anticipate future content, which is then utilized as a query to retrieve relevant documents to regenerate the sentence if it contains low-confidence tokens. We test FLARE along with baselines comprehensively over 4 longform knowledge-intensive generation tasks/datasets. FLARE achieves superior or competitive performance on all tasks, demonstrating the effectiveness of our method.
</div>

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/2305.06983">The paper: Active Retrieval Augmented Generation (Jiang et al., arXiv 2023)</a></div>

# Reference 

- Paper 
  - [ArXiv Version: Active Retrieval Augmented Generation (Jiang et al., arXiv 2023)](https://arxiv.org/abs/2305.06983)
  
- For Your Information
  - [Lil'Log's Gneralized Visual Language MOdels](https://lilianweng.github.io/posts/2022-06-09-vlm/)

- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

