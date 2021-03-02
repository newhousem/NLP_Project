# Twitter Natural Language Processing Project

## Purpose
The purpose of this project is to build a machine learning algorithm to predict the emotion of a tweet based on its content. To train the algorithm, the project will use tweets focused on a SXSW event that were manually categorized into positive and negative emotions. 

## Data Used

The data set was found on data.world
	https://data.world/crowdflower/brands-and-product-emotions

In the data set, 2978 tweets were categorized as expressing a positive emotion. 570 tweets were categorized as expressing a negative emotion. 

## Exploring the Data

![alt text](Images/Word%20Frequency%20in%20Positive%20Tweets.png)
![alt text](Images/Word%20Frequency%20in%20Negative%20Tweets.png)

Positive Tweets Word Map
![alt text](Images/Word%20Map%20Positive%20Tweets.png)

Negative Tweets Word Map
![alt text](Images/Word%20Map%20Negative%20Tweets.png)

As we can see from the graphs and the word maps, both emotions have many of the same words. The similarity between words in the tweets may make it difficult for the model to differentiate between the two emotions. 

To explore what words may be used in the models for each emotion, I ran an LDA model to look at the types of words within each emotional category. 

Positive Tweets
![alt text](Images/Positve%20Words%20Group%203.png)
Some words that can be seen in the groups of positive emotion tweets are; 'great', 'good', 'awesome'

Negative Tweets
![alt text](Images/Negative%20Words%20Group%201.png)
Some words that can be seen in the groups of negative emotion tweets are; 'suck', 'headache', and other expletives 

## Modeling
### Baseline Model

![alt text](Images/Baseline%20Model.png)
The baseline model was a random forest classifier model with tfidf as a vectorizer.
The model has clear overfitting, and is better at predicting the positive emotion than the negative emotion

## Final Models
### Multinomial Naive Bayes

![alt text](Images/NB%20Final%20Model.png)

* Multinomial Naive Bayes model performed the best.
* The model had the best ratio between correct negative predictions and correct positive predictions, and positive and negative recall scores.
* However, there is overfitting

### Random Forest Classifier

![alt text](Images/RF%20Final%20Model.png)

* This Random Forest model has less overfitting than the Naive Bayes model.
* However, its scores are lower overall.

## Interpretation 
* Tuning the models required balancing between positive emotion recall and negative emotion recall scores.
* Some models could predict all positive emotion tweets correctly, but were not able to predict any negative emotion tweets. 
* Bigrams were used in the model to help contextualize words
* A max features of 1500 was used.
* Some notable words used in the Random Forest model include;
    * ‘Design headache’
    * ‘Suck’
    * ‘Cool’
    * ‘Win’
    * ‘Need’

![alt text](Images/Top%2030%20Features.png)

## Conclusion
* A model can be developed to categorize the emotion of a tweet. 
* Some words used to categorize the tweet were;
    * ‘Design headache’
    * ‘Suck’
    * ‘Cool’
    * ‘Win’
    * ‘Need’
* More data is needed to better categorize the emotions, especially in the negative emotion category.
* A trade off between positive emotion recall and negative emotion recall was required.  
* Using bigrams, pairs of words, may help to provide context to improve the model. 
 
## Next Steps
* Collect more data, especially tweets with the negative emotion
* Integrate more tools to deal with overfitting like ensemble modeling methods and training more data. 
* Try other methods like PCA or undersampling to deal with the class imbalance. 


