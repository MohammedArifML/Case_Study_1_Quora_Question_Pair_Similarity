# Case_Study_1_Quora_Question_Pair_Similarity
Quora is a place to gain and share knowledge—about anything. It’s a platform to ask questions and connect with people who contribute unique insights and quality answers. This empowers people to learn from each other and to better understand the world.  Over 100 million people visit Quora every month, so it's no surprise that many people ask similarly worded questions. Multiple questions with the same intent can cause seekers to spend more time finding the best answer to their question, and make writers feel they need to answer multiple versions of the same question. Quora values canonical questions because they provide a better experience to active seekers and writers, and offer more value to both of these groups in the long term.

Credits: Kaggle.

## 1. Problem Statement

1. Identify which questions asked on Quora are duplicates of questions that have already been asked.
2. This could be useful to instantly provide answers to questions that have already been answered.
3. We are tasked with predicting whether a pair of questions are duplicates or not.
4. Sources/Useful Links
    Source : https://www.kaggle.com/c/quora-question-pairs
    
    Discussions : https://www.kaggle.com/anokas/data-analysis-xgboost-starter-0-35460-lb/comments
    
    Kaggle Winning Solution and other approaches: https://www.dropbox.com/sh/93968nfnrzh8bp5/AACZdtsApc1QSTQc7X0H3QZ5a?dl=0
    
    Blog 1 : https://engineering.quora.com/Semantic-Question-Matching-with-Deep-Learning
    
    Blog 2 : https://towardsdatascience.com/identifying-duplicate-questions-on-quora-top-12-on-kaggle-4c1cf93f1c30

## 2. Real world/Business Objectives and Constraints

1. The cost of a mis-classification can be very high.
2. You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice.
3. No strict latency concerns.
4. Interpretability is partially important.

## 3. Machine Learning Probelm 

### 3.1 Data 
### 3.1.1 Data Overview 
- Data will be in a file Train.csv
- Train.csv contains 5 columns : qid1, qid2, question1, question2, is_duplicate
- Size of Train.csv - 60MB
- Number of rows in Train.csv = 404,290
### 3.1.2 Example Data point 
"id","qid1","qid2","question1","question2","is_duplicate"

"0","1","2","What is the step by step guide to invest in share market in india?","What is the step by step guide to invest in share market?","0"

"1","3","4","What is the story of Kohinoor (Koh-i-Noor) Diamond?","What would happen if the Indian government stole the Kohinoor (Koh-i-Noor) diamond back?","0"

"7","15","16","How can I be a good geologist?","What should I do to be a great geologist?","1"

"11","23","24","How do I read and find my YouTube comments?","How can I see all my Youtube comments?","1"

### 3.2 Mapping the real world problem to an ML problem 
#### 3.2.1 Type of Machine Leaning Problem 
It is a binary classification problem, for a given pair of questions we need to predict if they are duplicate or not.

### 3.3 Performance Metric 
Source: https://www.kaggle.com/c/quora-question-pairs#evaluation
Metric(s):

1. log-loss : https://www.kaggle.com/wiki/LogarithmicLoss
2. Binary Confusion Matrix

### 3.4 Train and Test Construction 
We build train and test by randomly splitting in the ratio of 70:30 or 80:20 whatever we choose as we have sufficient points to work with.


## Courtesy: AppliedAI Course (www.appliedaicourse.com)
