# Transformer

Based on [Attention is All You Need](https://arxiv.org/abs/1706.03762)

### Overview

Transformer is a black-box model for machine translation. It consists of *Encoders*, *Decoders* and the links between them. Among them, there are equal amounts of *Encoders* and *Decoders* stacking together. Each encoder consists of a self-attention layer and a feed-forward layer. There is one additional attention layer in decoder, in order to pay attention to the relations in the input sentences. 

### Details
- self-attention:
    + first step, generate three vectors for each input word vector: query vector, key vector and value vector.
    + second step, calculate score for a word using each word in the sentence. This determines how important the word to other words in the sentence.
    + third and fourth steps, using softmax to normalize the scores.
    + fifth step, multiply each softmax score with each value vector.
    + sixth step, sum all weighted vectors.
- multi-head attention mechanism.
- Training
    + KL divergence.
    + Cross entropy.