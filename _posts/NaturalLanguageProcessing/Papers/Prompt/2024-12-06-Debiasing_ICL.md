---
layout: post
title: Debiasing In-Context Learning by Instructing LLMs How to Follow Demonstrations
subtitle: Debiasing In-Context Learning
category: Prompting
tags: [LLM, Propmt]
permalink: /2024/12/06/Debiasing_ICL/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [Debiasing In-Context Learning by Instructing LLMs How to Follow Demonstrations (Li et al., ACL-findings 2024)](https://aclanthology.org/2024.findings-acl.430/), that I read and studied. 

{% include MathJax.html %}

![Li et al. ACL-findings 2024](/img/Image/NaturalLanguageProcessing/Papers/Pompt/2024-12-06-Debiasing_ICL/debaising_ICL_01.png)

They proposed the solution to debiasing In-context Learning (ICL) they call demonstration bias, which is from the selection and order of demonstrations. 

To deal with demonstration bias, they propose two de-biasing strategies for in-context learning, 

1) Instance-Free Demonstration Reordering, which progressively selects demonstrations by maximizing the semantic ambiguity reduction of in-context demonstrations. 

2) Self-Explanatory In-Context Learing framework, which generates explicit explanatory guidelines for each instantce and then instructs LLMs to select appropriate semantic modes by following these guidelines.


For detailed experiment and explanation, refer to the paper, titled [Debiasing In-Context Learning by Instructing LLMs How to Follow Demonstrations (Li et al., ACL-findings 2024)](https://aclanthology.org/2024.findings-acl.430/)

<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note(Abstract): </b>
In-context learning(ICL) has gained considerable attention due to its data efficiency and task adaptability. Unfortunately, ICL suffers from the demonstration bias, i.e., its performance and robustness are severely affected by the selection and ordering of demonstrations. In this paper, we identify that such demonstration bias may primarily stem from the semantic ambiguity induced by demonstrations, i.e., a demonstration may indicate multiple input-to-label mappings and its mapping can be interpreted differently in different contexts by LLMs. Such semantic ambiguity disrupts task comprehension during ICL and results in performance fluctuations. To resolve the semantic ambiguity problem, this paper further proposes two de-biasing strategies to mitigate demonstration bias in in-context learning. Experiments on six datasets show that our methods can effectively alleviate demonstration bias and significantly improve task performance.
</div>

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://aclanthology.org/2024.findings-acl.430/">The paper: Debiasing In-Context Learning by Instructing LLMs How to Follow Demonstrations (Li et al., ACL-findings 2024)</a></div>


# Reference 

- Paper 
  - [ACL Version: Debiasing In-Context Learning by Instructing LLMs How to Follow Demonstrations (Li et al., ACL-findings 2024)](https://aclanthology.org/2024.findings-acl.430/)
   
- For Your Information
  - [Lil'Log's Prompt Engineering](https://lilianweng.github.io/posts/2023-03-15-prompt-engineering/)

- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

