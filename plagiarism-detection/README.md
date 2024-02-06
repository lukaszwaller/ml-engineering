# Plagiarism Detection
<img src="https://github.com/lukaszwaller/ml-engineering/blob/main/assets/plagiarism-detection.jpg" alt="plagiagrism detection" width="300"/>
*This image was generated with AI, Morty! You know, cutting-edge stuff from another dimension, burp?*

## Overview

So, Morty, we're building this fancy plagiarism detector. It's like a sci-fi tool that decides if a text is ripping off another text. We've got to be on our toes, Morty, because telling the difference between sneaky rewrites and original work is no picnic.

## Features and Comparison

To make this plagiarism gadget work, we've got to come up with some nifty features. The process involves defining similarity features that gauge the resemblance between a given Student Answer Text (the file requiring labeling) and a designated Wikipedia Source Text (considered the original source). It's like picking up clues, Morty. We've got[this paper](https://s3.amazonaws.com/video.udacity-data.com/topher/2019/January/5c412841_developing-a-corpus-of-plagiarised-short-answers/developing-a-corpus-of-plagiarised-short-answers.pdf) here that tells us about containment and longest common subsequence. Let's dive into those.

### Feature Calculation

Okay, Morty, we need to calculate how much these texts resemble each other. It's like looking for identical words in a sea of text. Ready for the ride?

## Classification Models

Now, we're not just playing around, Morty. We need a model, like a spaceship, to fly through our data and tell us if it's plagiarized or not. We've got to test these models out and see which one's the real deal.

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

The containment value tells us how chummy the texts are. It's like checking if they're secret best friends or just strangers.

## Longest Common Subsequence (LCS)

Alright, Morty, now we've got the Longest Common Subsequence (LCS). It's like finding the longest shared trail of words, but they don't have to be in order. It's like spotting a pattern in the chaos of words.

## Calculating and Interpreting LCS

To calculate the Longest Common Subsequence (LCS) between two sequences word-wise, follow these steps:

1. **Tokenization:**
   - Tokenize the sequences into words.

2. **Dynamic Programming:**
   - Utilize dynamic programming to find the LCS.
   (*It's a bit technical, Morty! burp*)

3. **Formula:**
   - LCS is calculated based on the common words rather than characters.

```markdown
LCS = (Length of the Longest Common Subsequence) / (Total Words in the Sequences)
```

Example:
Consider the sequences:

* Sequence A: "Morty, let's go on an adventure!"
* Sequence B: "Rick, let's embark on a quest!"


The LCS is "let's on." This represents the longest common subsequence, word-wise, shared between the two sequences.

Interpretation:
Finding an LCS word-wise is like unraveling the mysteries of the multiverse. The longer the LCS, the more harmonious the textual adventure, Morty! It's like deciphering the cosmic code of linguistic connections in the vast expanse of narratives across dimensions, you know?