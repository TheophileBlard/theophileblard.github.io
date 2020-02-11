---
title: "Training BERT on a large-scale French sentiment analysis dataset"

mathjax: True

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"

classes: wide
excerpt: "This blog post showcases how I built a large-scale dataset for French sentiment analysis, and what were my results by training BERT on it."
---

NLP is difficult (the most impacful ?)
BERT => one step towards solving NLP.
Pretrained on large text corpus with self-supervision (no need for annotating) in order to form a language model.
This language model can then be trained on a supervised task (and reach SOTA).
easy to use library: transformers (formerly, ..)

In xx-2019: Camembert : first BERT preètrained model fro french
=> added to transformers !

I was surprised to see : French : no large-scale dataset
This is what pushed me to build mine.

## Building the Dataset

Annotating text excerpts (eg: tweets) by myself was out of the question, as it would take months to gather a dataset of sufficient size.
I also decided not to use online crowdsourcing platforms like [Amazon Mechanical Turk](https://www.mturk.com/), because I couldn't afford to pay people for a personal project.

My approach is inspired by the [Large Movie Review Dataset](https://ai.stanford.edu/~amaas/data/sentiment/), better known as the IMDb dataset.
This is a dataset for binary sentiment classification containing 50k highly polar movie reviews, collected from [imdb.com](https://www.imdb.com/).
Using the rating associated with each user review, the authors automatically annotated reviews with their sentiment (a negative review has a score $$ \leq 4 $$ out of $$10$$, and a positive review has a score $$ \geq 7 $$ out of $$ 10 $$).

<p align="center">
    <img src="/assets/french_sentiment_analysis/allocine/rating_counts.png" width="700" >
    <figcaption>Caption describing these two images.</figcaption>
</p>

## Training BERT

TODO

## How good is BERT ?

comparing

TODO
