## TOPIC MODELING AND EMOTION CORRELATION FROM CONVERSATIONS
### Project By - Sara Khanjani & Shreepriya Dogra, UMBC
### Project Advisor - Dr. Karen Chen, UMBC

### ABSTRACT
- Transcripts of Customer Calls can be processed and analyzed using state-of-the-art NLP models to get meaningful insights. 
- Some of the insights that can be drawn are about the Crucial Topics or Areas of Concern, Emotions associated with the conversation depicting Satisfaction Level of Customer and Correlation with other available data like the Speakers, Length of call, etc. 
- Our aim in the first phase of the project is to find the main topics of conversation and also if these topics are correlated with certain emotions. 
- We used some Python-based preprocessing to get the data into a format that was useful to the analysis. 
- We tried some basic topic modelling to get a feel of the topic words generated. 
- We simplified the problem into a simple Binary Classification task to understand if the predominant could be predicted using the words in the text as features.
- Random Forest was used for analysis which did not perform well for the current dataset due to its small size and possible noise. 

A small video describing the work is below - 

<iframe width="560" height="315" src="https://www.youtube.com/embed/H7xcnrfm9oU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### MOTIVATION

 - Transcripts of conversations Customer Calls can be processed and analyzed using state-of-the-art NLP models

- Key Performance Indicators - 
  - Crucial Topics - Areas of Concern 
  - Emotions - Satisfaction Level of Customer
  - Correlation with other available data - Speakers 


### DATASET & EXPLORATORY DATA ANALYSIS

Dataset has been taken from https://sail.usc.edu/iemocap/. 
It has the following main characteristics - 
- Conversational
- Provided with Emotion Labels
- Open Dataset

Reference - 
Interactive Emotional Dyadic Motion Capture (IEMOCAP)
C. Busso, M. Bulut, C.C. Lee, A. Kazemzadeh, E. Mower, S. Kim, J.N. Chang, S. Lee, and S.S. Narayanan, "IEMOCAP: Interactive emotional dyadic motion capture database," Journal of Language Resources and Evaluation, vol. 42, no. 4, pp. 335-359, December 2008. 

The raw data features can be seen below.

<img width="799" alt="RawDataset" src="https://user-images.githubusercontent.com/1511050/147159575-b11797f9-0779-4876-8571-ba5f616b99a8.png">

The final dataset features can be seen below.

<img width="788" alt="FinalDataset" src="https://user-images.githubusercontent.com/1511050/147159590-6e6d8441-f7ed-4b6d-87ab-a7071e7eeeb4.png">

The initial dataset has a lot of unnecessary words, which are shown below.

<img width="847" alt="Exploratory Data" src="https://user-images.githubusercontent.com/1511050/147159988-c7441960-99ca-4b98-a0c5-f4318bf463e2.png">

#### DATA PREPROCESSING
1. Removal of Non-English Conversations
2. Removal of -
   - Punctuations
   - Upper Case Letters 
   - Stop Words 
3. Tokenization - Breaking down text data into smaller units

A repeat of visualization of top words shows that more meaningful words are now showing up.

<img width="787" alt="PreProcesed" src="https://user-images.githubusercontent.com/1511050/147160401-54d135e6-c2a9-4371-92fe-c30139bee789.png">

### MODEL DEVELOPMENT
The model has two major parts - 
- Unsupervised 
- Supervised

#### OBJECTIVES - METHODS - MODELS

<img width="839" alt="Screenshot 2021-12-22 at 4 08 35 PM" src="https://user-images.githubusercontent.com/1511050/147160664-23d47ba9-3308-42ef-8834-23d136d41440.png">

#### 1. TOPIC MODELLING
- Topic Modelling gave us 9 Topics.
- Each Topic has Topic words associated with it.

Sample visualization of the topic words has been presented. A visual inspection shows that the words look similar.


<img width="307" alt="Screenshot 2021-12-22 at 4 19 57 PM" src="https://user-images.githubusercontent.com/1511050/147161538-ce1b44d3-bd16-4e54-8ea6-59a8c2c03820.png">
<img width="304" alt="Screenshot 2021-12-22 at 4 19 50 PM" src="https://user-images.githubusercontent.com/1511050/147161545-54df4fce-d7bd-4fca-8052-9dcf9e0f59ab.png">
<img width="296" alt="Screenshot 2021-12-22 at 4 19 39 PM" src="https://user-images.githubusercontent.com/1511050/147161554-295dd5cd-e5c0-45a4-8ba5-89fb2d0e4f0f.png">

#### 2. EMOTION PREDICTION USING TFIDF FEATURES

- In this method feature extraction is done by the TFIDF Vectorizer. This step maps words to a corresponding vector of real numbers. The number of features extracted initially was 3218. 
- After this feature reduction using Principal Component Analysis (PCA) was done. PCA is a linear dimensionality reduction method. After this step the number of final features was reduced to 91, keeping the variance in data 95%.
- INPUT - 91 features 
- OUTPUT - Emotion Label - 0/1 representing Negative/Positive respectively
- Next, we perform a Binary Classification using Random Forest. Random Forest with different depths will be tried to avoid overfitting.


<img width="682" alt="Screenshot 2021-12-22 at 4 46 25 PM" src="https://user-images.githubusercontent.com/1511050/147163531-88e04f84-c7f4-4fc9-9be3-2b65336e4309.png">


#### 3. EMOTION PREDICTION USING LDA FEATURES
- In this method we start with the tokenization of text. We have used Gensim (https://radimrehurek.com/gensim/). It is a free Python library for topic modelling. It does the creation of Bag-of-words, Gensim dictionary and corpus. 
- We obtain 144 LDA Features.
- INPUT - 144 features 
- OUTPUT - Emotion Label - 0/1 representing Negative/Positive respectively
- Next we perform a Binary Classification using Random Forest. Random Forest with different depths will be tried to avoid overfitting.

<img width="789" alt="Screenshot 2021-12-22 at 4 43 15 PM" src="https://user-images.githubusercontent.com/1511050/147163267-2ae6c12d-9b39-43f8-a5e8-0752231b4848.png">


### RESULTS
The results have been divided into two parts. 

#### EMOTION PREDICTION USING TFIDF FEATURES
<img width="356" alt="Screenshot 2021-12-22 at 4 23 59 PM" src="https://user-images.githubusercontent.com/1511050/147161816-c6887b05-3089-49dc-a507-c6471d00d23e.png">



#### EMOTION PREDICTION USING LDA FEATURES
<img width="341" alt="Screenshot 2021-12-22 at 4 25 38 PM" src="https://user-images.githubusercontent.com/1511050/147161957-47ce2e16-3aac-42ce-9fcd-f409bab56bf1.png">


### CONCLUSION
- Both models do not perform well.
- Random Forest on TFIDF Features is overfitting.
- Random Forest on LDA Features give more realistic results, but not the best model.
- New models need to tried to get an appropriate model for our dataset and problem statement.


### FUTURE WORK
- Create/get access to relevant datasets as the current dataset is very small for our analysis.
- Create profiles and ratings for customer service executives based on duration of call & customer experience. The speakers can be identified as a customer or customer service executive. Customer experience can be judged by the change in emotions and the final emotion at the end of the call. 
- Analyse duration of calls and experience (change of emotions) of customers to identify if there is a cut-off time after which executives are not able to resolve customer problems.
- Analyse duration & frequency of calls and link it with the associated topics.

### TEAM REFLECTION
The project has been no less than an adventure. Our top learnings and reflections are enumerated here. First and foremost, finding an appropriate dataset is crucial for the analysis. Secondly, conversion of the raw data into a ready to use dataset is a big task. Spend a lot of time on EDA. Lastly, try several different models. Real-life data may be noisy and may not give the expected results in one go.

### ACKNOWLEDGMENTS
We would like to thank Dr. Karen Chen for her constant support, advice and feedback. We would also like to thank Dr. Vandana Janeja for suggesting the problem statement. Last but not the least, we would like to thank the IEMOCAP team for providing us the dataset to us, very promptly. 
