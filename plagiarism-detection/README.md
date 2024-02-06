# Plagiarism Detection
<img src="https://github.com/lukaszwaller/ml-engineering/blob/main/assets/plagiarism-detection.jpg" alt="plagiagrism detection" width="300"/>
*This image was generated with AI, Morty! You know, cutting-edge stuff from another dimension, burp?*

## Overview

This project involves building a plagiarism detector that classifies a given text file as either plagiarized or not, based on its similarity to a provided source text. Detecting plagiarism is a challenging task, considering the subtle differences between paraphrased content and original work.

## Features and Comparison

To facilitate plagiarism detection, the process involves defining similarity features that gauge the resemblance between a given Student Answer Text (the file requiring labeling) and a designated Wikipedia Source Text (considered the original source). Further information on the features described can be found in [this paper](https://s3.amazonaws.com/video.udacity-data.com/topher/2019/January/5c412841_developing-a-corpus-of-plagiarised-short-answers/developing-a-corpus-of-plagiarised-short-answers.pdf). Notably, features such as containment and longest common subsequence are recommended.

### Feature Calculation

The subsequent sections detail the calculation of these features, providing insights into comparing the two texts. The goal is to extract relevant features that will aid in the classification process.

## Classification Models

Upon the extraction of features, the responsibility entails a thorough exploration of diverse classification models. Conduct a meticulous evaluation to discern and select a model that showcases optimal performance when assessed against a designated test dataset.

*Note: The successful completion of this task necessitates careful consideration and systematic experimentation to attain proficient plagiarism detection.*

## Containment

Containment is a measure used to assess the similarity between a submitted text and a source text based on the occurrence of n-gramswhich are contiguous sequences of n items (words or characters).

### Calculating Containment

To calculate containment, follow these steps:

1. **N-gram Counts:**
   - Utilize count vectorization to calculate the n-gram counts for both the submitted and source texts.

2. **Formula:**
   - Apply the containment formula:
   $$\frac{\sum count(ngram_A) \cap count(ngram_S)}{\sum count(ngram_A)}$$

3. **Interpretation:**
   - If the two texts share no common n-grams, the containment is 0.
   - If all their n-grams intersect, the containment is 1.
   - Longer common n-grams may suggest cut-and-paste plagiarism.

The containment value provides insight into the degree of similarity between the texts, aiding in the identification of potential plagiarism.

