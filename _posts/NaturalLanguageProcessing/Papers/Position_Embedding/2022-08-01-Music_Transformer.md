---
layout: post
title: Music Transformer - Generating Music with Long-Term Structure
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

This post is a brief summary about the paper that I read for study and curiosity, so I shortly arrange the content of the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJe4ShAcF7), that I read and studied. 

{% include MathJax.html %}

The original paper by([Vaswani et al. NIPS 2017](https://papers.nips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html)) for transformer architecture uses positin encoding in input layer.

However, this paper proposes the efficient relative position embedding for music generation applying the method from [Shaw et al., NAACL 2018](https://aclanthology.org/N18-2074/).

They argue that for music generation, since timing and pitch is repeatedly generated, they take advantage of self-attention mechanism approach based relative position embedding to music generation task. 

As a result, they are saying that a Transformer with their relative attnetion mechanism maintains the regular timing grid present in the JSB Chorales dataset.

For the detailed method about representating music as a token seqeunce to apply autoregressive problem on music generation, refer to the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJe4ShAcF7).

On this article, I focus on explaining how to formularizing the relative position embedding on self-attention mechanisms. 

As you can see the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJe4ShAcF7), 

[Shaw et al., NAACL 2018](https://aclanthology.org/N18-2074/) introducesd relative position embedding to allow attention to be informed by how far two position are apart in a sequence. 

This intution causes model to make a separate relative position embedding, but they use relative bias score added to logit in self-attention mechanism as follows:

$$RelativeAttention = Softmax(\frac{QK^T + S^{rel}}{\sqrt(D_h)})V$$


The equation above is takeaway for relative poisiton embedding they proposed.


For detailed experiment and explanation, refer to the paper, titled [Music Transformer: Generating Music with Long-Term Structure, Huang et al. ICLR 2019](https://openreview.net/forum?id=rJe4ShAcF7).

    
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
