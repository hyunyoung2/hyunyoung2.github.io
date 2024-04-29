---
layout: post
title: UnifiedSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models
subtitle: UnifiedSKG
category: Text2SQL
tags: [Text2SQL, Semantic_Parsing, NL2SQL]
permalink: /2024/04/22/UnifiedSKG/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [UnifiedSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models (Xie et al., EMNLP 2022)](https://aclanthology.org/2022.emnlp-main.39/), that I read and studied. 

{% include MathJax.html %}

They proposed the UNIFIEDSKG framework to standardize datasets, models, code, experiments, and evaluation metrics into a single framework by casting user requeests, structured knowledge, and outputs into the text-to-text format as follows.
 
![Xie et al., EMNLP 2022](/img/Image/NaturalLanguageProcessing/Papers/Knowledge/2024-04-22-UnifiedSKG/UnifiedSKG_figure1.png)

The following is the task unification, which is six task families , on UnifiedSKG into text-to-text format.

![Xie et al., EMNLP 2022](/img/Image/NaturalLanguageProcessing/Papers/Knowledge/2024-04-22-UnifiedSKG/UnifiedSKG_figure2.png)

   - **Semantic Parsiong** converts questions to logical forms.
   - **Question Answering** derives answers to natural language questions based on structured data.
   - **Data-to-Text generation** describes structured data in natural language.
   - **Fact Verfication** checks if a statement is true based on the structured data.
   - **Conversational Task** require understanding of not only the user's last request but also the full interaction history between users and machines.
   - **Formal Language to Text Translation** describes formal language in natural language.
     
The all tasks above take as input a user request, a structured knowledge input, and an optional (dilaogue) context to predict an output y.

For detailed experiment and explanation, refer to the paper, titled [UnifiedSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models (Xie et al., EMNLP 2022)](https://aclanthology.org/2022.emnlp-main.39/)

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://aclanthology.org/2022.emnlp-main.39/">The paper: UnifieSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models (Xie et al., EMNLP 2018)</div>

# Reference 

- Paper 
  - [ArXiv Version: UnifiedSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models (Xie et al., arXiv 2022)](https://arxiv.org/abs/2201.05966)
  - [EMNLP Version: UnifiedSKG: Unifying and Multi-Tasking Structured Knowledge Grounding with Text-to-Text Language Models (Xie et al., EMNLP 2022)](https://aclanthology.org/2022.emnlp-main.39/)
    
- Leaderboard & Github
  -  [SKG Github](https://github.com/xlang-ai/UnifiedSKG)
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

