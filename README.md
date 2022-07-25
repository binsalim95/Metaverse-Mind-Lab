# Metaverse-Mind-Lab
Take Home Assessment

The overall approach:

THe overall approach for this is simple - I'll look at cleaning out the text data using a preprocessing Pipeline, vectorize it using a Tf Idf Vectorizer and then use an XGBoosted Random Forest Model. I decided to go with XGBoost over Naive Bayes, Passive Aggressive and BERT classifiers as it is more robust to overfitting and literature shows that Tree Based methods usually outperform Neural Nets on Tabular Data (ref: https://arxiv.org/abs/2106.03253v1). Although with more text data, we can use a neural net which can outperform an XGBoost provided we have enough data and computational resources.

The preprocessing steps:

The Preprocessing steps were fairly simple: I got rid of new line characters, contractions (don't --> do not), stop words (Useless Filler words like "the", "and", etc), punctuations and from there I lowercased all words so that there wouldn't be any issues with case sensetivity.


Evaluation procedure and metrics:

I vectorized the cleaned text using the TF IDF Vectorizer and then ran the vector through the XGBoosted Random Forrest Model. The two metrics I used were Accuracy and F1 Score. I also tried evaluating the XG Boosted model against Naive Bayes and the Passive Aggressive classifier. XG Boost outperformed Naive Bayes and the Passive Aggressive Classifier on Accuracy. 


Aspects that could be improved:

In next iterations, we could try stemming and lemmatizing the words before vectorization. We can use different word Embedding procedures (LDA, word2vec, seq2vec etc) to see if different word vectors will produce better results. We can also have the model include the source of the news and the title of the article as well in its evaluation. We can also run a sentiment analysis and use a subjectivity score as well on the reviews and take those into account into the next model. We can also have multiple models running on top of the XGBoost forrest to see if we see improvements in performance.


