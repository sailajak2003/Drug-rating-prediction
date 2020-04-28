
# Drug rating prediction using NLP

  In this project I used NLP to predict ratings for a drug based on the reviews. The idea is not only to see how deep learning frameworks can be used to predict the sentiment of various reviews but also to see how the outliers behave esp. if the review and the actual rating are actually far.

I used **Spacy** for the NLP processing and **Tensorflow** as my deep learning framework to predict the ratings.

Here is a quick explanation of how i did this.
 
#### 1. Data Exploration
 
I am using  data from Kaggle.

This data has more than 215,000 rows and 7 columns. Other than "Rating" our target column, I looked at the rest of the columns and did some exploratory analysis in the first part. I used seaborns  to look at various columns like top rated drugs, top rated conditions and simillarly worst rated drug and conditions etc.


#### 2.EDA

#### Most of the ratings are 8 and higher. Denser at ends

![Image description](https://github.com/sailajakarra/Drug-rating-prediction/blob/master/images/download.png)


#### This plot explains some of top 10 drugs with 10 rating
![Image description](https://github.com/sailajakarra/Drug-rating-prediction/blob/master/images/download%20(1).png)


#### This plot explains some of top 10 drugs with 1 rating
![Image description](https://github.com/sailajakarra/Drug-rating-prediction/blob/master/images/download%20(2).png)



#### This plot explains some of top 10 conditions with 10 rating
![Image description](https://github.com/sailajakarra/Drug-rating-prediction/blob/master/images/download%20(3).png)



#### This plot explains some of top 10 conditions with 1 rating
![Image description](https://github.com/sailajakarra/Drug-rating-prediction/blob/master/images/download%20(4).png)
          
           
#### 3. Feature Engineering 
 
Here I looked at the reviews and did  Tokenizing, stop word removal, sequence to vector, and padding.

Word cloud show some of the commonly used words in the dataset.

![Image description](https://github.com/sailajakarra/Drug-rating-prediction/blob/master/images/download%20(5).png)



#### 4. Modelling
**Bi-Directional LSTM**: I have read in various blogs that LSTM is the go to model for NLP, so my first model for this was Bi-Directional LSTM. Unfortunately it didn't quite live up to the hype, or may be i needed to spend a bit more time tuning the hyper parameters. Anyways here is the chart of my model.

<img src="/images/Bi_Directional_LSTM.png"  width="400" height="400">

**Conv-1D**: The next model i created was a Convolutional model. These are more popoular with computer vision and image analysis but I got a better result with Conv-1D for NLP than Bi-Directional LSTM. Also for this dataset this model was extremely fast, so i was able to tune this better.

<img src="/images/Conv1D.png"  width="400" height="450">

**Conv1D+LSTM:** After I realized how Conv1D was getting better results compared to Bi-Directional LSTM, i created a new model that had both Conv1D layer feeding LSTM. This is the best model i could come up for this project.

<img src="/images/Conv1d_LSTM.png"  width="400" height="500">

#### 4. Final Result
Based on the various models, the best performing model is **Conv1D+LSTM**.With a Test score of 1.64 and Test accuracy of 0.62

