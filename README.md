# Bilingual Named Entity Machine Translation
Build a French-Vietnamese Low Resource Machine Translation

### Datasets Files format
French-Vietnamese Bilingual corpora (on request) <br />

### Tools to use
* Moses (Koehn, 2009) : http://www.statmt.org/moses_steps.html 
* nmt-keras (Peris, 2017) to train a neural network transliteration machine, https://github.com/lvapeab/nmt-keras/ <br />

## Benchmark 
* IWSLT English-Vietnamese : <br />
https://github.com/tensorflow/nmt#iwslt-english-vietnamese <br />
Data: https://nlp.stanford.edu/projects/nmt/data <br />
Train: 133K examples, vocab=vocab.(vi|en), train=train.(vi|en) dev=tst2012.(vi|en), test=tst2013.(vi|en), download script.

### Training details. 
We train 2-layer LSTMs of 512 units with bidirectional encoder (i.e., 1 bidirectional layers for the encoder), embedding dim is 512. LuongAttention (scale=True) is used together with dropout keep_prob of 0.8. All parameters are uniformly. We use SGD with learning rate 1.0 as follows: train for 12K steps (~ 12 epochs); after 8K steps, we start halving learning rate every 1K step.
