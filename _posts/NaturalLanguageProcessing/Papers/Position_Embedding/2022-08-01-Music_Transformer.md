---
layout: post
title: Music Transformer - Generating Music with Long-term Structure
subtitle: Title of paper - Music Transformer - Generating Music with Long-Term Structure
category: Transformers - Position Embedding
tags: [Trainsformer, position]
permalink: /2022/08/01/Music_Transformer/
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

This article is brief summary about the paper that I read for study and curiosity, so I shortly arranges the content of the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJ), that I read and studied. 

{% include MathJax.html %}

The original paper([Vaswani et al. NIPS 2017](https://papers.nips.cc/paper/2019/hash/9d63484abb477c97640154d40595a3bb-Abstract.html)) use positin encoddeing in input layer.

In addition, this paper proposes efficient relative position embedidng for music generation unlike [Shaw et al., NAACL 2018](https://aclanthology.org/N18-2074/).

they argue that for music generation, since timing and pitch is repeatedly generated, they extend self-attention mechanism approach based relative position embedding to music generation task. 

As a result, a Transformer with their relative attnetion mechanism maintain the regular timing grid present in the JSB Chorales dataset.

For detailed way about represent as token music to approach autoregressive problem on music generation, refer to the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJ).

On this article, I focus on the relative position embedding on self-attention mechanisms. 

As you can see the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJ), 

[Shaw et al., NAACL 2018](https://aclanthology.org/N18-2074/) introducesd relative position embedding to allow attention to be informed by how far two position are apart in a sequence. 

This intution causes a separate relative position embedding, but they use relative score added to logit for self-attention as follows:

$$RelativeAttention = Softmax(\frac{QK^T + S^{rel}}{\sqrt(D_h)})$$


The equation above is takeaway for relative poisiton embedding they proposed.


For detailed experiment and explanation, refer to the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJ).

    
<div class="alert alert-success" role="alert"><i class="fa fa-paperclip fa-lg"></i> <b>Download URL: </b><br>
  <a href="https://openreview.net/forum?id=rJe4ShAcF7">The paper: Music Transformer: Generating Music with Long-Term Structure (Huang et al., ICLR 2019)</a>
</div>

# Reference 

- Paper 
  - [ICLR Version: Music Transformer: Generating Music with Long-Term Structure (Huang et al., ICLR 2019)](https://openreview.net/forum?id=rJe4ShAcF7)
  
- How to use html for alert
  - [how to use icon](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_icons.html)
 
- How to use MathJax 
  - [MathJax basic tutorial and quick reference in StackExchange](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)
