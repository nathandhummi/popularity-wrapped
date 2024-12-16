# Main document:

**i. the data set your team used**

The dataset used in this project is the Spotify Tracks Dataset, containing information on 114,000 songs collected from Spotify. It includes metadata such as track_name, artists, album_name, and track_genre, along with detailed audio features like popularity, danceability, energy, tempo, valence, loudness, and instrumentalness. Other attributes include explicit (whether the track contains explicit content), key (musical key), mode (major or minor), duration_ms (track length), and time_signature.

**ii. the overview of the problem your team addressed**

We wanted to explore what auditory features influenced the popularity of a song on Spotify. We wanted to see if we could predict if a song was “popular” or “unpopular”. 

**iii. the key methodology that worked to address the problem with explanations as to why**

To address the problem of figuring out what key variables affect a song’s classification of “popular” or “unpopular”, random forest was the best methodology when looking at performance results and accuracy in its predictions. First off, it achieved a very high accuracy of 97.98%, the highest among the models trained. In addition, the AUC score for the Random Forest model was 0.788, indicating that it was the best model to differentiate between “popular” and “unpopular” songs. In addition, the model is very robust to overfitting as it utilizes bootstrap aggregation and trains trees on slightly different datasets. This reduces the variance of the individual trees so the final model generalizes better to unseen data. Finally, the random forest model gives us key insights into feature importance. This is done by calculating how much each feature reduces impurity, or GINI index, across splits in the decision trees. We see that tempo and loudness influenced popularity most, at 12.3% each. Instrumentalness was least important at 8.2%.

**iv. results including cross-validation used and evaluation metrics and conclusions such as why you chose the key method and its limitations**

Logistic Regression achieved an accuracy of 95.75% but struggled with class imbalance, often misclassifying popular songs. KNN performed slightly better, with an accuracy of 95.5% at k=9, but lacked interpretability and scalability for larger datasets. Random Forest outperformed both, achieving an accuracy of 97.98% and providing valuable insights into feature importance, with tempo, loudness, and acousticness being key predictors of song popularity. PCA effectively reduced dimensionality by identifying components that captured most of the data’s variance, while clustering provided insights into grouping patterns, though it was not central to classification. Neural Networks matched Logistic Regression in accuracy but required significant computational resources and struggled with class imbalance, similar to other models. For cross-fold validation, we opted to use 5 folds to separate training into 4 of those sets and validation into one, for each iteration. Evaluation metrics such as accuracy, confusion matrices, precision, recall, and ROC-AUC were used to assess performance. With these metrics, we can see that the Random Forest model was the most accurate and easiest to generalize with the most confidence. Although it still has the limitation of having a low true positive rate of about 57.79%, it was the best model to fit our data set.

**v. how to use the code for your project on the data set.**

To use our code, please make sure to run the first two cells and install all the proper packages. To load the dataset, first find the dataset by going to https://huggingface.co/datasets/maharshipandya/spotify-tracks-dataset and downloading the data set. Then upload the corresponding file to your Google Colab, Jupyter Notebook, etc. and load this data using the third cell of code.
