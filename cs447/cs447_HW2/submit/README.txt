CS 447, Fall 2015
Homework 2

This directory contains 11 files:

 (1)    README:                 This file
 (2)    hw2.pdf:                PDF handout with description of the assignment

Part 1: Hidden Markov Model POS Taggers (6 points)
 Code:
 (3)    hmm_sanity_check.py:    Test script for Part 1 (provided to validate your code)
 (4)    hw2_hmm.py:             Stub Python module for bigram HMM tagger
 (5)    hw2_hmm_eval.py:        Stub Python module for evaluating your tagger

 Data:
 (6)    train.txt:              Tagged POS training data
 (7)    test.text:              Raw POS test data
 (8)    gold.text:              Tagged POS test data

Part 2: Pointwise Mutual Information (4 points)
 Code:
 (9)    pmi_sanity_check.py:    Test script for Part 2 (provided to validate your code)
 (10)   hw2_pmi.py:             Stub Python module for calculating PMI of movies.txt corpus

 Data:
 (11)   movies.txt:             Movie review corpus for PMI calculation



***********************************************************************************************
*  Please note that you are not allowed to share the data with people outside of this class.  *
*  Furthermore, you must delete the three data files at the end of this semester.             *
***********************************************************************************************
HMM
Implements bigram HMM model for POS tagging. Laplace smoothing done with defaultdict(lambda: 1).
Accuracy and F-measure scores are poor but reflect the true accuracy of the tagger. 5% POS tagging
which is better than random but far worse than the expected 92% accuracy. I suspect an indexing error 
but I can't seem to find it. Computations done in log space. Words below a wordcount threshold are changed to UNK


PMI
Counts duplicate words in a sentence. Initial read of movies done by sorting the sentence and
looking at a smaller subset of pairs. The same method is used for finding top-k. Top-k uses a heap to store and find top-k
Finding top-100 with k=2 takes ~13 min on my low power VM
