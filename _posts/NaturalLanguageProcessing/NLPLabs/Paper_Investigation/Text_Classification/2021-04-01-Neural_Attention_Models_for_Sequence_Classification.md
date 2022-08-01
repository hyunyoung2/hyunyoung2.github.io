---
layout: post
title: Neural Attention Models for Sequence Classification- Analysis and Application to Key Term Extraction and Dialogue Act Detection
subtitle: Title of paper - Neural Attention Models for Sequence Classification- Analysis and Application to Key Term Extraction and Dialogue Act Detection
category: NLP papers - Language Model
tags: [neural network, text classification]
permalink: /2021/04/01/Neural_Attention_Models_for_Sequence_Classification/
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

This is a brief summary of paper for me to study and organize it, [Neural Attention Models for Sequence Classification: Analysis and Application to Key Term Extraction and Dialogue Act Detection (Shen and Lee, arXiv 2016)](https://arxiv.org/abs/1604.00077) that I read and studied. 
{% include MathJax.html %}


They propose sequence classificaiton model conbining long short-term memory(LSTM) with attention mechanism like the following figure:

![From Shen and Lee, arXiv 2016](/img/Image/NaturalLanguageProcessing/NLPLabs/Paper_Investigation/Text_Classification/2021-04-01-Neural_Attention_Models_for_Sequence_Classification/NN_ATT_MODEL.PNG)

As you can see Figure 1, first they summarize a input sequence as a fixed-size vector  which is output vector \\(O_T\\) of LSTM and then use the summarized vector \\(O_T\\) and input seqeunce vector \\(V = \(V_1, V_2, ..., V_T\)\\) for attention mechanism. 

For all the parameters in embedding layer, they are shared in input of LSTM and attention mechanism.

In the figure 1, embedding layer denotes a linear transforamtion matrix.

Before digging into attention mechanism, Let's see several annotations.

   - The set \\(x = \(x_1, x_2, ..., x_T\)\\) denotes input sequence,  where T is the sequence length. Each element in \\(x\\) represent a fixed-length featur vector.
   
   - The word embedding set \\(V = \(V_1, V_2, ..., V_T\)\\) indicates input seqeunce vectors. 
   
   - \\(O_T\\) denote output vector which can be regarded as the summariess of the preceding feature vector.
   
   - The set \\(e = \(e_1, e_2, ..., e_T\)\\) denotes a list of score.
   
   - The set \\( \alpha = \(\alpha_1, \alpha_2, ..., \alpha_n\)\\) denotes a list of attention weight.

When the calculate score between output vector and input sequence vector, they use cosine similarity.

$$ e_i = O_T \odot V_i $$

Where \\(\odot\\) denotes cosine similarity between the summarizaed output vector \\(O_T\\) and input vector \\(V_i\\)

They also normalized the score for attention mechanism in two ways.

For sharpening, it use the softmax to normalizae socres. 

$$\alpha_i = \frac{exp(e_i)}{\sum_{i=1}^T exp(e_i)}$$

For smoothint, they changed the exponential function in equation above with logisitic sigmoid function \\(\\\), 

$$\alpha_i = \frac{\sigma(e_i)}{\sum_{i=1}^T \sigma(e_i)}$$

With their model and attention machanism, they carried out two sequence classification task.

 - Dialogue act(DA) detection: it is about categorizing the intention behind the speaker's move in conversation.
 
 - Key term extraction: its goal is to automatically extract relevant terms from a given document.

For detailed experiment analysis, you can found in [Neural Attention Models for Sequence Classification: Analysis and Application to Key Term Extraction and Dialogue Act Detection (Shen and Lee, arXiv 2016)](https://arxiv.org/abs/1604.00077)
  
<div class="alert alert-info" role="alert"><i class="fa fa-info-circle"></i> <b>Note(Abstract): </b>
Recurrent neural network architectures combining with attention mechanism, or neural attention model, have shown promising performance recently for the tasks including speech recognition, image caption generation, visual question answering and machine translation. In this paper, neural attention model is applied on two sequence labeling tasks, dialogue act detection and key term extraction. In the sequence labeling tasks, the model input is a sequence, and the output is the label of the input sequence. The major difficulty of sequence labeling is that when the input sequence is long, it can include many noisy or irrelevant part. If the information in the whole sequence is treated equally, the noisy or irrelevant part may degrade the classification performance. The attention mechanism is helpful for sequence classification task because it is capable of highlighting important part among the entire sequence for the classification task. The experimental results show that with the attention mechanism, discernible improvements were achieved in the sequence labeling task considered here. The roles of the attention mechanism in the tasks are further analyzed and visualized in this paper.
</div>
    
<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://arxiv.org/abs/1604.00077">The paper: Neural Attention Models for Sequence Classification: Analysis and Application to Key Term Extraction and Dialogue Act Detection (Shen and Lee, arXiv 2016)</a>
</div>

# Reference 

- Paper 
  - [arXiv Version: Neural Attention Models for Sequence Classification: Analysis and Application to Key Term Extraction and Dialogue Act Detection (Shen and Lee, arXiv 2016)](https://arxiv.org/abs/1604.00077)
  
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
    


