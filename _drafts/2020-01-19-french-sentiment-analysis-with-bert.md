---
title: "Training BERT on a large-scale French sentiment analysis dataset"

header:
  overlay_image: images/posts/french-sentiment-analysis-with-bert/camemBERT.png
  overlay_filter: 0.5

mathjax: True

toc: true
toc_label: "Table of Contents"
toc_icon: "cog"

excerpt: "The goal of this project was to train a BERT-based model on a large-scale dataset in French language. For this purpose, we're going to build our own sentiment analysis dataset, and train several models on it."
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
This is a dataset for **binary sentiment classification** containing 50k highly polar movie reviews, collected from [imdb.com](https://www.imdb.com/).
Using the rating associated with each user review, the authors automatically annotated reviews with their sentiment (a negative review has a score $$ \leq 4 $$ out of $$10$$, and a positive review has a score $$ \geq 7 $$ out of $$ 10 $$).

[Allociné](http://www.allocine.fr) is basically a French IMDb.
It contains user and critic reviews over dozens of thousands of films and TV shows, more than enough for our purpose !
In order to build our dataset, we're going to extract reviews from Allociné web pages.

![image-center]({{ base_path }}/images/posts/french-sentiment-analysis-with-bert/allocine_logo.png){: .align-center}
Allociné Logo
{: style="text-align: center;"}
{: .small}

### Web scraping

Automatically extracting content from websites is called **web scraping**.
Web scraping programs look for specific HTML tags or CSS selectors in the code source, in order to retrieve data, in a targeted way.
By taking advantage of the structured nature of web pages, these programs can iterate over the whole website and recover a large amount of data without any human labor.

For this project, I decided to


![image-center]({{ base_path }}/assets/french_sentiment_analysis/allocine/rating_counts.png){: .align-center}
Original vs. calibrated images
{: style="text-align: center;"}
{: .small}

### Exploring data


## Training BERT

TODO

## How good is BERT ?

comparing

TODO
