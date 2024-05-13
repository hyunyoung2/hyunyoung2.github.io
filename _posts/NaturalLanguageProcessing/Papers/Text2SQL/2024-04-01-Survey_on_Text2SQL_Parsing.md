---
layout: post
title: A Survey on Text-to-SQL Parsing - Conctps, Methods, and Future Directions
subtitle: Text2SQL parsing Survey
category: Text2SQL
tags: [Parsing, Text2SQL]
permalink: /2024/04/01/Survey_on_Text2SQL_Parsing/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [A survey on Text-to-SQL Parsing: Concepts, Methods, and Future Directions (Qin et al., arXiv 2022)](https://arxiv.org/abs/2208.13629), that I read and studied. 

{% include MathJax.html %}

Recently, the generative model in deep learning have significantly advanced the text2SQL task regarding LLM as mapping function from natural language question to an output SQL query.

This paper provides a comprehensive review on deep learning approaches for text-to-SQL parsing.

This paper presented three points such 1) Whether Text-to-SQL copora is single-turn or multi-turn, 2) pre-trained language model and existing method for text-to-SQL parsing, 3) future and potential challenges for text-to-SQL Parsing.

Futhermore, this paper explained the evaluation metric for Text2SQL. 

The text-to-SQL is evaluated by comparing the generated SQL with the ground-truth SQL answer. Concretely, there are two types of evaluation metrics that are used for evaluting the single-turn setting, including exact set match accuracy (EM) and execution accuracy (EX). For the multi-turn setting, question match accuracy (QM) and interaction match accuracy (IM) are commonly employed.

For single-trun text2SQL evaluation 

  - Exact Set Match Accuracy (EM) is cacluated with vlaues by comparing the ground-truth SQL query and the predicted SQL query. Both ground-truth query and the predicted SQL query are parsed into normalized data structures which have the following SQL ""SELECT"", ""GROUP BY"", ""WHERE"", ""ORDER BY"", ""KEYWORD""(including all SQL keywords without column names and operators).

  - Execution Accuracy (EX) is calculated with values by comparing the output results of executing the ground-truth SQL query and the predicted SQL query on the database contents shipped with the test set.

For multi-turn text2SQL evalution

   - Question Match Accuracy (QM) is calculated as the EM score over all questions.

   - Interaction Match Accuracy (IM) is calculated as the EM score over all interactions (question sequences).

The following indicate that corpora for learning and evaluating the text-to-SQL(T2S) parsing system.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_table2.png)

In the figure above, single-turn denotes context-independent & multi-turn is context-dependent. Especially, the SPIDER dataset is widely used on constructing the Text2SQL Parsing system as benchmark.

Deep learing has long been dominant in the field of text-to-SQL parsing, yielding state-of-the-art performances. The following provide a comprehensive review of recent neural network-based approaches for text-to-SQL parsing.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_table3.png)

For Text2SQL modeling, Sequence-to-sequence model has widely used in the Text2SQL parsing system. 

The follwoing figure 2 explained that encoder should be able to recognize linking structure, schema structure, question structure.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_figure2.png)

First of all, the linking structure is schema linking which is to identifying references of columns, tables, and condition values in text. In other words, text2SQL parser should learn to detect table or column names mentioned in text by matching question tokens with schema.

The following figure explained the decoder used in exiting Text-to-SQL parsing models can be divided into two categories: sketch-based methods and generation-based methods.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_figure3.png)

The following how to leverage contextual information in text2SQL Parsing system.
Especially, the following indicates how to learning the multi-turn input representation. 

Asid from learning the multi-turn input representation, decouples the multi-turn text2SQL parsing into two pipeline tasks which are question rewrting (QR) and single-turn text2SQL parsing.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_figure4.png)

So far, they focus on the text2SQL parsing modeling, The following indicates pre-training data construction for text2SQL parsing tasks.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_table4.png)

The following is the pre-training objective for text-to-SQL parsing.

![Qin et al., arXiv 2023](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-01-Survey_on_Text2SQL_Parsing/text2SQL_survey_dataset_table5.png)

For detailed explanation, refer to the paper, titled [A survey on Text-to-SQL Parsing: Concepts, Methods, and Future Directions (Qin et al., arXiv 2022)](https://arxiv.org/abs/2208.13629)

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/2208.13629">The paper: A Surevey on Text-to-SQL Parsing: Concepts, Methods, and Future Directions (Qin et al., arXiv 2022)</a> </div>

# Reference 

- Paper 
  - [ArXiv Version: A survey on Text-to-SQL Parsing: Concepts, Methods, and Future Directions (Qin et al., arXiv 2022)](https://arxiv.org/abs/2208.13629)
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

