
# Drug rating prediction using NLP

  In this project I use NLP to predict ratings for a drug based on the reviews. The idea is not only to see how deep learning frameworks can be used to predict the sentiment of various reviews but also to see how the outliers behave esp. if the review and the actual rating are actually far.

I use **Spacy** for the NLP processing and **Tensorflow** as my deep learning framework to predict the ratings.

Here is a quick explanation of how i did this.
 
#### 1. Data Exploration
 
We are using [company name] data from Kaggle.

This data has more than 215,000 rows and 7 columns. Other than "Rating" our target column, we look at the rest of the columns and did some exploratory analysis in the first part. I used seaborns **countplot** to look at various columns like top rated drugs, top rated conditions and simillarly worst rated drug and conditions etc.
          
           
#### 2. Feature Engineering 
 
Here we look at the factors and do some factor engineering steps

**Tokenize:**  {here goes what is Tokenize}

**Stop Word Removal:** [something about removing stop words]

**Sequence to Vector:** { what is seq2vec, why is this important, any drawbacks?}

**Padding**: {simple why padding, one setence is good} 


#### 3. Modelling
**Bi-Directional LSTM**: I have read in various blogs that LSTM is the go to model for NLP, so my first model for this was Bi-Directional LSTM. Unfortunately it didn't quite live up to the hype, or may be i needed to spend a bit more time tuning the hyper parameters. Anyways here is the chart of my model.

<img src="/images/Bi_Directional_LSTM.png"  width="400" height="400">

**Conv-1D**: The next model i created was a Convolutional model. These are more popoular with computer vision and image analysis but I got a better result with Conv-1D for NLP than Bi-Directional LSTM. Also for this dataset this model was extremely fast, so i was able to tune this better.

<img src="/images/Conv1D.png"  width="400" height="450">

**Conv1D+LSTM:** After I realized how Conv1D was getting better results compared to Bi-Directional LSTM, i created a new model that had both Conv1D layer feeding LSTM. This is the best model i could come up for this project.

<img src="/images/Conv1d_LSTM.png"  width="400" height="500">

#### 4. Final Result
Based on the various models, the best performing model is **Conv1D+LSTM**.
