---
layout: post
title: Length-Controlled AlpacaEval - A Simple Way to Debias Automatic Evaluators
subtitle: alpacaeval 2.0
category: LLMEVAL
tags: [LLM, LLMEval, Reward]
permalink: /2024/07/20/alpacaEval2/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [Length-Controleed AlpacaEval: A Simple Way to Debias Automatic Evaluators (Dubois et al., arXiv 2024)](https://arxiv.org/abs/2404.04475), that I read and studied. 

{% include MathJax.html %}

In this paper, they want to focus on operatinalizing "what would be the AlpacaEval metric be, if the output of all models had the same lengthas those of the baseline?" into a simple regression-based estimator.

In other words, The automated evaluation measures such as AlpacaEval return their quality estimates through a combination of direct effects that measure the quality of model response and indirect effects that are mediated by spurious variables such as the length of outputs. 


![Dubois et al., arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/LLMEval/2024-07-20-alpacaEval2/AlpacaEval2_01.png)

The following is length control via regression. 
 - Model Identity
 - Length of output
 - Instruction difficulty

![Dubois et al., arXiv 2024](/img/Image/NaturalLanguageProcessing/Papers/LLMEval/2024-07-20-alpacaEval2/AlpacaEval2_02.png)


For detailed experiment and explanation, refer to the paper, titled [Length-Controleed AlpacaEval: A Simple Way to Debias Automatic Evaluators (Dubois et al., arXiv 2024)](https://arxiv.org/abs/2404.04475)

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/2404.04475">The paper: Length-Controlled AlpacaEval: A Simple Way to Debias Automatic Evaluators (Dubois et al., arXiv 2024)</a></div>

# Reference 

- Paper 
  - [ArXiv Version: Length-Controleed AlpacaEval: A Simple Way to Debias Automatic Evaluators (Dubois et al., arXiv 2024)](https://arxiv.org/abs/2404.04475)


- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
  - [List of Greek letters and math symbols](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols)
