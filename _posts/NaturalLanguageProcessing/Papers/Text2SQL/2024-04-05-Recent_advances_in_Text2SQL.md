---
layout: post
title: Recent Advances in Text-to-SQL: A Survey of What We Have and What We Expect
subtitle: Recent Advances in Text-to SQL
category: Text2SQL
tags: [Survey, Text2SQL]
permalink: /2024/04/05/Recent_advances_in_Text2SQL/
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

This post is a brief summary about the paper that I read for my study and curiosity, so I shortly arrange the content of the paper, titled [Recent Advances in Text-to-SQL: A Survey of What We Have and What We expect (Deng et al., Coling 2022)](https://aclanthology.org/2022.coling-1.190/), that I read and studied. 

{% include MathJax.html %}

Text2SQL has attracted attention from both natural language processing and database communities. 

That is beacuase the ability to convert the semantics in natural language into SQL queries.

Text-to-SQL is to convert natural utterance into SQL queries as in the following figure 1.

As you can see the figure 1, tiven a user utterance "What are the major cities in the state of Kansas?", the system outputs a corresponding SQL that can be used for retrieving the answer from a database.
They survey the recent progress on text-to-SQL, from 1) datasets and 2) methods to 3) evaluation.

![Deng et al., Coling 2022](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-05-Recent_advances_in_Text2SQL/Recent_text2SQL_advances_figure1.png)

As shown in Table 1, existing text2SQL datasets can be calssified into three categories: 1) single domain dataset, 2) cross-domain, and others.

![Deng et al., Coling 2022](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-05-Recent_advances_in_Text2SQL/Recent_text2SQL_advances_table1.png)

In the case of method for Text2SQL parsing, they divide the methods employed in text-to-SQL research into 1) Data Augmentation, 2) Ecoding, 3) Decoding, 4)  Learnig Techniques, and 5) Miscellanenous.

The following is the typical methods used for encoding in the Text2SQL.

They group encoding methods into five categories as shown in Table 2. 

![Deng et al., Coling 2022](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-05-Recent_advances_in_Text2SQL/Recent_text2SQL_advances_table2.png)

The following is typical mtehods used for decoding in text-to-SQL.

![Deng et al., Coling 2022](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-05-Recent_advances_in_Text2SQL/Recent_text2SQL_advances_table3.png)

![Deng et al., Coling 2022](/img/Image/NaturalLanguageProcessing/Papers/Text2SQL/2024-04-05-Recent_advances_in_Text2SQL/Recent_text2SQL_advances_table4.png)

For detailed experiment and explanation, refer to the paper, titled [Recent Advances in Text-to-SQL: A Survey of What We Have and What We expect (Deng et al., Coling 2022)](https://aclanthology.org/2022.coling-1.190/)

<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://aclanthology.org/2022.coling-1.190/">The paper: Recent Advances in Text-to-SQL: A Survey of What We Hav and What We Expect (Deng et al., Coling 2022)</div>

# Reference 

- Paper 
  - [ArXiv Version: Recent Advances in Text-to-SQL: A Survey of What We Have and What We expect (Deng et al., arXiv 2022)](https://arxiv.org/abs/2208.10099)
  - [Coling Version: Recent Advances in Text-to-SQL: A Survey of What We Have and What We expect (Deng et al., Coling 2022)](https://aclanthology.org/2022.coling-1.190/)
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

