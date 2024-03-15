---
layout: default 
title: "Models"
---

# Methods

## The Data
We aquired photos of poles around San Diego in different times of day and different angles manually as a team. To replicate the abilities of the average person, the photos are intentionally imperfect to give the data more realistic features. The text dataset was taken from a project named ['HumAID'](https://crisisnlp.qcri.org/humaid_dataset) that collected tweets made during natural disasters. It was chosen because they were short and we expect reports from customers no longer than around a paragraph. Additionally the data included topics that should be related to forms of damage done to poles. 

## The Models
Three models were necessary to create the product: DeTr, SVM, and a VADER model for the photos and text. DeTr a detection transformer model used for images of poles,

## Detr Model
For the first layer in our platform, the goal is to validate whether or not the submitted image contains a pole so we optimized DeTr, a pre-trained object detection model, on 1500 valid images of poles collected from the Google Street View API. As our product accepts data in the form of manually taken images, we trained the model with an additional 515 manually captured photos from different angles, times of day and exposures with the intention of accommodating different users. 

It works by combining a back bone, for DeTr it is a resnet50, that makes an image into a 2d representation. Then feeds to a transformer to calculate the features in the image, in our case poles. Then a feed forward network that makes the final decision for a prediction on whether or not a pole is detected.

## Text Models
As for the second layer, we performed text analysis to identify the topic and urgency of potential pole issue descriptions that the platform would accept. To do this, two different NLP models are used, SVM for topic classification and a VADER model for sentiment analysis. 

## SVM Model
While researching different models to use for our text analysis, we found that linear SVM were best suited for our goal to classify text into several categories. To use SVM, we preprocessed the text to represent vectors of n dimensions where each word in the text is a single dimension. This model works by reducing the dimensionality of the vectors and creating multiple decision boundaries with varying weights, allowing for accurate classifications. We trained the SVM model on the HumAID data to categorize the text into “infrastructure_and_utility_damage” and “requests_or_urgent_needs” labels. While labels are not ideal, this provides a measure of usability in the future when more helpful labels may be used to better identify the urgency of an asset’s condition such as “fire”, “tilt”, and “minor malfunction”.   

## Vader Model

Along with the categorization of topics, we want to prioritize the issues for each of these categories. To do this we used VADER,  a pre-trained sentiment analysis model which assesses the emotional tone of customer reports by giving a Neutral, Positive, or Negative score. These sentiment scores can then be ranked based on their emotional urgency. This model is trained on the HumAID dataset and optimized to identify pole issue related words at varying negativity levels like “flame” and “smoke”. 

Valence Aware Dictionary and sEntiment Reasoner or Vader works by having a large lexicon of sentiment related words to determine the overall sentiment of a text. Words have sentiment ratings that reflect the positivity or negativity. For example ‘great’ has a positive sentiment rating so it could be rated 3. While a word like ‘tragedy’ is perceived as negative and could have a score of -3. We customized the lexicon by adding hazardous equipment based words with sentiment ratings. It does not require much preprocessing to work because it has this large lexicon so typical training expected of sentiment analysis was not necessary. We chose it for the ease of use and effectiveness on short texts reflective of the model’s intended purpose of use in social media settings. 



[back](./)
