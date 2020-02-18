---
title: "Training BERT on a large-scale sentiment analysis dataset in French language"

header:
  overlay_image: images/posts/french-sentiment-analysis-with-bert/camemBERT.png
  overlay_filter: 0.5

mathjax: True

toc: true
toc_label: "Table of Contents"
toc_icon: "file-alt"

excerpt: "The goal of this project is to train **BERT** on a **large-scale French dataset**. For this purpose, we're going to build our own **sentiment analysis** dataset, and train other *state-of-the-art* models, so that we can put BERT results in context."
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

Annotating text excerpts (eg: *tweets*) manually was out of the question, as it would be so time-consuming that it would take months to gather a dataset of sufficient size.
I also decided not to use online *crowdsourcing* platforms like [Amazon Mechanical Turk](https://www.mturk.com/), because I can't afford to pay people for a personal project.

My approach is inspired by the [Large Movie Review Dataset](https://ai.stanford.edu/~amaas/data/sentiment/) {% cite maas2011learning %}, better known as the IMDb dataset.
This is a dataset for **binary sentiment classification** that contains 50k highly polar movie reviews, collected from [imdb.com](https://www.imdb.com/).
Using the rating associated with each user review, the authors automatically annotated reviews with their sentiment (a negative review has a score $$ \leq 4 $$ out of $$10$$, and a positive review has a score $$ \geq 7 $$ out of $$ 10 $$).

[Allociné](http://www.allocine.fr) is basically a French IMDb.
It contains user and critic reviews over dozens of thousands of movies and TV shows, more than enough for our purpose !
In order to build our dataset, we're therefore going to extract reviews from Allociné web pages.

**Note:** For this project, I decided to focus on movies reviews made by users, thus leaving aside critic reviews and TV shows reviews.
Critic reviews are rarely meaningful anyway, as many of them are just excerpts of articles posted on another website.
{: .notice--info}

![image-center]({{ base_path }}/images/posts/french-sentiment-analysis-with-bert/allocine_logo.png){: .align-center}
Allociné Logo
{: style="text-align: center;"}
{: .small}

### Web scraping

Automatically extracting content from websites is a process called **web scraping**.
Web scraping programs look for specific *HTML tags* or *CSS selectors* in the source code, in order to retrieve data in a targeted way.
By taking advantage of the structured nature of web pages, these programs can iterate over whole websites and recover a large amount of data without any human labor.

On Allociné, films are distinguished from each other by their *film id*, which simply is a positive integer.
All user reviwes URLs follow the same pattern:
`http://www.allocine.fr/film/fichefilm-22092/critiques/spectateurs/`

but those ids are sparse and unpredictible








Following {% cite maas2011learning %}, I only extracted 30 reviews per movie because reviews for the same movie tend to have correlated ratings (also time)
### Exploring data

![image-center]({{ base_path }}/assets/french_sentiment_analysis/allocine/rating_counts.png){: .align-center}
Original vs. calibrated images
{: style="text-align: center;"}
{: .small}


## Training BERT

TODO

## How good is BERT ?

comparing

TODO


## References
----------

{% bibliography --cited %}