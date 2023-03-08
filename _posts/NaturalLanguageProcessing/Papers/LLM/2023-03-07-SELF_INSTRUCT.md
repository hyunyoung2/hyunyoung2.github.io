---
layout: post
title: SELF-INSTRUCT  
subtitle: Title of paper - SELF-INSTRUCT; Aligning Language Model with Self Generated Instructions
category: LLM - Instruction
tags: [LLM, Instruction, Self-training]
permalink: /2023/03/07/SELF_INSTRUCT/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper titled [SELF-INSTRUCT: Aligning Language Model with Self Generated Instructions. Wang et al., arXiv 2022](https://arxiv.org/abs/2212.10560) that I read and studied. 

{% include MathJax.html %}

Addressing large instruction-tuned language model, They propose some way to resolve the fact that intruction-tuned LLM(large language model)s depend on human-written instruction data that is limited in quantity, diversity, and creativity. 

So, they instroduce a frome called SELF-INSTRUCT to improve the intruction-following capabilities of pretrained language models by sampling it own generations.

Let's see the framework below

![Wang et al., arXiv 2022](/img/Image/NaturalLanguageProcessing/Papers/LLM/2023-03-07-SELF_INSTRUCT/Self-Instruct_figure.png)

The pipleline of the SELF-INSTRUCT consists of generating instruction, input, and output sample. 

Let's see the definition of Instruction Data

A set of instructions ${I_t}$, each of which defines a task $t$ in natural language. Each task has one or more input-output instances $(X_t, Y_t)$. A Moel $M$ is expected to produce the output $y$, given the task instruction $I_t$, and the instance input $x$.

Note that intruction and instance input does not have a strict boundary in many case.

For example, an instruction "write an essay about school safety" can be reformulated as "write an essay about the following topic" as the instruction, and "school safety" as an instance input.

They also took into account the diversity of the data format,so they composed such instructions that don require addtional input ("i.e., x is empty")

Continually, see the process of their automatic instruction data generation. 

Their pipeline for generation the instruction data consists of four steps:
 
1) instruction gneration
2) identifying whether instruction represents a classification task or not
3) instanc generation with the input-first or output-first approach
4) filtering low-quality data.

Finally, after the abvoe process, They fine-tuned the LM(Language model to follow instruction to evaluate their method. 

If you want to know and understand the detailed information about SELF-INSTRUCT, Read the paper which titled [SELF-INSTRUCT: Aligning Language Model with Self Generated Instructions. Wang et al., arXiv 2022](https://arxiv.org/abs/2212.10560)
     
Futhermore, If you want to their large synthetic dataset, visit their [github](https://github.com/yizhongw/self-instruct)     
     
<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/2212.10560">The paper's title is known as SELF-INSTRUCT: Aligning Language Model with Self Generated Instructions (Wang et al., arXiv 2022)</a>
</div>

# Reference 

- Paper 
  - [arXiv Version: SELF-INSTRUCT: Aligning Language Model with Self Generated Instructions (Wang et al., arXiv 2022)](https://arxiv.org/abs/2212.10560)
  
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
