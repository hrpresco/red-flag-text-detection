# “Red Flag” Text Detection

This is a repository for exploring transformer-based text classification for identifying “red-flag” text, including e.g., depressive speech, cyberbullying, hate speech, offensive speech, etc. See the Project Writeup section below for information on background, goals, work completed so far and follow-on work.

# Project Writeup

## Motivation

* Mental health challenges are currently highly prevalent among American teens. \[1\] E.g. depression, anxiety, etc.
* Toxic behavior such as cyberbullying is also a major issue faced by American teens \[2\].
* As a teen, I have witnessed these challenges first hand, and am motivated to help find solutions.
* Social media is playing an ever more important role \[3\]
  * As a platform for toxic behavior
  * As a forum where mental health issues are often displayed.
* The goal of this work is to use social media posts for early detection of problem behavior and mental health issues.

## Background

* Text classification is a task within the Natural language processing (NLP) domain that is applicable to the above goal
  * Toxic behavior such as cyberbullying and hate speech and signs of mental health challenges can be identified as classes of text using natural language techniques.


* Transformers are a recent breakthrough in deep learning with specific application to NLP tasks such as text classification, producing state of the art performance.

### Transformers

* Recently-developed type of deep learning model based on an Attention mechanism \[4\].
* Previous deep learning architecture used for text classification were recurrent neural networks (RNNs).
* Transformers provide a critical advantage over RNNs: they can be trained in parallel (rather than serially), making it practical to train them with much larger data sets, yielding much better model prediction performance.
* Citations for more info.

## Approach

* The  goal of the work is to evaluate the effectiveness of using transformer models to identify examples of bullying and hate speech, and possible signs of depression from online social media posts.
* The initial focus was on cyberbullying and depressive speech.
  * This early focus was driven largely by readily available training data in these two focuses; training data relating specifically to hate speech was more difficult to find.
* A pre-trained BERT model \[5\] was used as the starting model for fine tuning.
  * BERT is pre-trained using the BooksCorpus and English Wikipedia data sets (consisting of around 3.3 billion words combined)
* The model was fine tuned on depressive speech using a combination of two depression-related datasets taken from similar projects in Github
* __[niquejoe](https://github.com/niquejoe)__/**[Classification-of-Depression-on-Social-Media-Using-Text-Mining](https://github.com/niquejoe/Classification-of-Depression-on-Social-Media-Using-Text-Mining)**
* [Allenfp](https://github.com/Allenfp)/**[DepressionDetectionNLP](https://github.com/Allenfp/DepressionDetectionNLP)**
* For each data set, 90% of the data were used for the training process itself, and the remaining 10% for evaluation. The model was trained using 6 epochs.
* The process was then repeated to train the model on examples of cyberbullying using the data set from Wang et al \[6\].

## Results

## Follow-on Work

* Expand the datasets used to train the models that classify cyberbullying and depressive speech to get a more accurate prediction. We could do this by collecting our own data and assembling it into a diverse dataset.
* Train a model specifically on hate speech data.
* Combine our depression, cyberbullying, and hate speech-related models using an ensamble technique to build a model that is capable of classifying red-flag text as belonging to any one of these three categories.

## Citations



1. Balingit, Moriah. "‘A cry for help’: CDC warns of a steep decline in teen mental health", The Washington Post, March 31, 2022, <https://www.washingtonpost.com/education/2022/03/31/student-mental-health-decline-cdc/>. August 13, 2022.
2. Anderson, Monica. “A Majority of Teens Have Experienced Some Form of Cyberbullying.”, Pew Research Center, September 27, 2018, [pewresearch.org/internet/2018/09/27/a-majority-of-teens-have-experienced-some-form-of-cyberbullying/](http://pewresearch.org/internet/2018/09/27/a-majority-of-teens-have-experienced-some-form-of-cyberbullying/). August 13, 2022.
3. Nixon, Charisse. “Current perspectives: the impact of cyberbullying on adolescent health”, National Library of Medicine, August 1, 2014, <https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4126576/>. August 13, 2022.
4. Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, Illia Polosukhin (2017). Attention Is All You Need. ([link](https://arxiv.org/abs/1706.03762))
5. Devlin, Chang, Lee, Toutanova (2018). BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding. ([link](https://arxiv.org/abs/1810.04805))
6. J. Wang, K. Fu, C.T. Lu, “SOSNet: A Graph Convolutional Network Approach to Fine-Grained Cyberbullying Detection,” Proceedings of the 2020 IEEE International Conference on Big Data (IEEE BigData 2020), December 10-13, 2020

   \


