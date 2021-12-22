## TOPIC MODELING AND EMOTION CORRELATION FROM CONVERSATIONS
### Project By - Sara Khanjani & Shreepriya Dogra, UMBC

### ABSTRACT
- Transcripts of Customer Calls can be processed and analyzed using state-of-the-art NLP models to get meaningful insights. 
- Some of the insights that can be drawn are about the Crucial Topics or Areas of Concern, Emotions associated with the conversation depicting Satisfaction Level of Customer and Correlation with other available data like the Speakers, Length of call, etc. 
- Our aim in the first phase of the project is to find the main topics of conversation and also if these topics are correlated with certain emotions. 
- We used some Python based preprocesing to get the data into a format that was useful to the analysis. 
- We tried some basic topic modelling to get a feel of the topic words generated. 
- We simplied the problem into a simple Binary Classification task to understand if the predominant could be predicted using the words in the text as features.
- Random Forest was used for analysis which did not perform well for the current dataaset due to it's small size and possible noise. 

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
It has the following main characterictics - 
- Conversational
- Provided with Emotion Labels
- Open Dataset

Reference - 
Interactive Emotional Dyadic Motion Capture (IEMOCAP)
C. Busso, M. Bulut, C.C. Lee, A. Kazemzadeh, E. Mower, S. Kim, J.N. Chang, S. Lee, and S.S. Narayanan, "IEMOCAP: Interactive emotional dyadic motion capture database," Journal of Language Resources and Evaluation, vol. 42, no. 4, pp. 335-359, December 2008. 

The raw datas features can be seen below.
<img width="799" alt="RawDataset" src="https://user-images.githubusercontent.com/1511050/147159575-b11797f9-0779-4876-8571-ba5f616b99a8.png">

The final dataset features can be seen below.
<img width="788" alt="FinalDataset" src="https://user-images.githubusercontent.com/1511050/147159590-6e6d8441-f7ed-4b6d-87ab-a7071e7eeeb4.png">


### MODEL DEVELOPMENT
describe the pipeline from raw data to processed data to model development
Flowchart helps

### RESULTS & INSIGHTS 
Present a few results
Make sure you interpret it correctly 

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
- Finding an appropriate dataset is crucial for the analysis.
- Conversion of the raw data into a ready to use dataset is a big task.
- Spend a lot of time on EDA.
- Try several different models. Real-life data may be noisy and may not give the expected results in one go.

### ACKNOWLEDGMENTS
- We would like to thank Dr. Karen Chen for her constant support, advice and feedback.
- We would like to thank Dr. Vandana Janeja for the problem statement.
- We would like to thank the IEMOCAP team for providing us the dataset.
