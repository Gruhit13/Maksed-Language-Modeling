# Maksed-Language-Modeling
Understanding the importance of word based on the words before and after it.
======

## Overview
------
The approach was to use model to predict the [mask] word in a given sentence. 

For that purpose I used transformer model with self-attentions along with multiple heads. Transformer is a bi-directional model
and thus uses the text ahead and after the **[mask]** token to predict the perfect word that mathces the sentence and also seems grammetically 
correct, which is important for sustaining the true sense of the sentence.

This project was inspired from BERT (Bi-directional Encoder Representation from Transformer) which was developed by google to overcome the computational
time expense of LSTM in addition to providing parellel computing supportability, which is useful wiht GPU. Transfomer has show a high rise in domain of NLP.
It is being used in almost all the task that are concern from NLP and hence inspiring from that I decided to learn the working of a transformer and hence came across
BERT

[BERT Paper](https://arxiv.org/pdf/1810.04805.pdf)

## My Appraoch
------

Although their are a lot of python library available for providing pre-trained transformer I was much eager to develop one of my own in order to get a through sense of
how exactly things work in it. Hence I developed an entire transformer for the specific task of **Masked Language Modeling**. The main aspect in it to cover was implementation
of Multi-headed Attention that resides at the core of transformer and is responsible for concentrating on varying part of sentence, in a manner similar to how a human do.

For example for a given sentence: There was a **[mask]** near the river bank. A normal human will focus on the river bank in order to predict the right word for the **[mask]**.
That's excatly what a Multi-headed attention do.

[Attention is all you need](https://arxiv.org/pdf/1706.03762.pdf)

## Model Architecture
------

My model architecture was totally inspired from that of BERT but on a miniature scale. I used 4 Heads, Model size of 128, Width of model to be 128 and 2 layers. Despite with
minimal configurations the model size was upto +3M parameters. One of the cause why transformer overfits.

## Dataset
------
I combined IMDB movies review dataset with the ROC stories dataset in order to satisfy 2 task
1) Getting long range sentences, fulfilled by IMDB dataset
2) Getting a meaning ful sentneces, fulfilled by ROC stories dataset.

The main reason for combining this two dataset is firstly I needed a dataset that is has a satsifying sequence length in addition to a meaningful sentences. IMDB has large
reviews but the sentences may or may not be syntatically correct on the other hand ROC dataset is a syntatically correct but has small sequences and thus to overcome this
problem I merge both of those dataset. But using either of those dataset can also work. 

## How to use bert?
------
I have provided the pretrained weights with following configuration
| Parameter | Value |
| :---: | :---: |
| Sequence Length | 64 |
| Model Size | 128 |
| Feed Forward Dimension | 128 |
| Attention Heads | 8 |
| Multiheaded Attention layers | 2 |

This is cofiguration of my model, for which I have provided a pretrained weights which thus can be finetuned by training for more time over the same dataset as well as some
others too. If you want my code then you can mail me at [Mail here](mailto:gruhitspatel15@gmail.com?subject=[Github]%20Request%20for%20Encoders)
