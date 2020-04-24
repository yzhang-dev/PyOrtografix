# PyOrtografix

[![MIT License][license-image]][license-url]

**PyOrtografix** is a seq2seq model with attension for ***automatic orthographic simplification***, based on PyTorch 1.4.

PyOrtografix is derived from a project offered by METL at University of Geneva.

## Automatic Orthographic Simplification

In the project, we will explore the power of using seq2seq models for automatic orthographic simplification, namely, for inferring spelling simplification rules directly from conventional text data. 

Here, we hypothesize that the task of automatic orthographic simplification can be approximated to a task of (character based) ***neural machine translation*** (**NMT**).

More specifically, it is equivalent to transcribing text from traditional English spelling to ***SoundSpel*** ([Rondthaler and Lias, 1978](https://ieeexplore.ieee.org/document/6592434)) , a proposed simplified spelling system for English.

## Tasks

### Understanding the data: annotating

Get familiar with the SoundSpel rules, then create a test set to evaluate the model (compare predicted and gold sequences of tokens using the [***Edit Distance***](https://en.wikipedia.org/wiki/Edit_distance), [Levenshtein Distance](https://en.wikipedia.org/wiki/Levenshtein_distance) or [Damerau-Levenshtein distance](https://en.wikipedia.org/wiki/Damerau%E2%80%93Levenshtein_distance)).

- [x] Training set (representative of all the rules detailed in Table B1, B2, and H1 to H6 of the SoundSpel proposal)
- [ ] Development/Validation set (optional)
- [ ] Test set 

#### Requirements

* Following the structure of the training set, create a set of  tokenized tab-separated word/sentence pairs **not** already contained in the training data.
* The test data should be **balanced** and **comprehensive** with respect to the rules already covered in the training set and the rules detailed in Table A to Table F of the SoundSpel proposal.
* The test set should contain **at least 10%** of the training set size (around 1818 word pairs in total), that is, around 200 word pairs.
* Sentences can be selected from the Wikipedia sample.
* A test set of around 400 word pairs will allow us to divide further between a development and a test set.

### Formulating a hypothesis: modeling

Try and find the best possible variant of the [**seq2seq**](https://d2l.ai/chapter_recurrent-modern/seq2seq.html) model for the task following the [PyTorch tutorial](https://pytorch.org/tutorials/intermediate/seq2seq_translation_tutorial.html) and [ortografix](https://github.com/akb89/ortografix). 

The aforementioned model is a character-based model that processes sequences of word pairs. It contains a GRU-based Encoder, a standard GRU-based Decoder. We play with the following variants:

- [ ] [**RNN**](https://d2l.ai/chapter_recurrent-neural-networks/index.html), [**GRU**](https://d2l.ai/chapter_recurrent-modern/gru.html) or [**LSTM**](https://d2l.ai/chapter_recurrent-modern/lstm.html) in the [**Encoder and Decoder**](https://d2l.ai/chapter_recurrent-modern/encoder-decoder.html)
- [ ] with and without [**Attention**](https://d2l.ai/chapter_attention-mechanisms/index.html) in the Decoder
- [ ] with and without [**Bidirectionality**](https://d2l.ai/chapter_recurrent-modern/bi-rnn.html) in the Encoder
- [ ] with and without [**Stacking**](https://d2l.ai/chapter_recurrent-modern/deep-rnn.html) in the Encoder and Decoder
- [ ] with and without [**Dropout**](https://d2l.ai/chapter_multilayer-perceptrons/dropout.html) in the Encoder and Decoder

### Validating the hypothesis: experimenting



### Output, evaluation and conclusion



## Install

To install PyOrtografix



## Train

To train a model



## Evaluate

To qualitatively evaluate the output of training on a dataset