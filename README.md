# populartweets
Predicting popular tweets for an effective social media marketing

First, run 1-Scraping. This section results in scrapped tweets of the companies mentioned in Fortune.xlsx. Alternatively, you can only run Entertainment section, because the project is based on the companies in the entertainment sector. Then proceed with preperation and modeling steps.

Social media platforms are undoubtedly the most hype formations of recent years and they increase their sphere of influence by increasing the number of members day by day and by making existing members more loyal users. One of the social media platforms, twitter has successfully emerged as a popular platform for expressing thoughts, opinions, and promoting various entities. The tweets posted on twitter, which is mostly used by individual users and frequently used for exchange of opinions, are valuable to the extent that they reach other users, otherwise the ideas that are not shared do not carry any value. Therefore, the more widely the tweets penetrate, the more the information carried by the tweet will reach the same width, and this will increase the success of the tweet. When a tweet's reader retweets a tweet that he or she has read, the tweet becomes visible to those who follow the retweeter, thus spreading the tweet to a wider audience. The study of how widely a tweet can spread, i.e. how popular it will be, is nothing new and goes back to the early days of twitter. However, we also see that many studies have been done just to make predictions without clarifying the benefit of this prediction to whom. The motivation for this research has been to initiate and conduct this study by targeting audiences who will benefit as much as possible while making predictions about popular tweets. For this reason, the focus is on social media marketing, and the companies that carry out this marketing on twitter have been chosen as the focus group.

Within the scope of this project, CRISP-DM methodology was followed in order to have a guided path and to ensure that the tasks are separated both among themselves and on the temporal line. The CRISP-DM methodology is a process that aims to increase the use of data mining and achieve accurate results in a wide variety of business applications and industries. CRISP-DM is a six-step process to achieve a successful outcome in data mining projects. 

![image](https://github.com/ardahiz/populartweets/assets/81987695/805d020e-2710-404f-a63d-73581e789ef8)


1-Scraping corresponds to data understanding, while 2-Preparation consists data preparation. 3-Modeling notebooks covers the modeling, evaluation and deployment steps.

Business understanding part was carried out in parallel with research gap finding and literature review. In this part, it is decided who can benefit from the project and how and who will be the main stakeholders. Normally, the difficulty of the business understanding part arises when there are different executives of the project: Since the business value to be created as a result of the project differs according to the project executives with different proficiency and professional fields, it can be challenging to find a common business value. However, no such difficulties were encountered in this project. How the industry group, which is thought to be beneficial, and how the companies are selected, is mentioned in the Business understanding section.

Within the scope of Data understanding, the needs of the project were elaborated, and it was determined which data would be collected, from which sources and by which methods. Therefore, in this step, it was aimed to collect all data for the target. Within the scope of data understanding, the tweets of the selected companies were obtained using a 3rd party scraping tool and the data shape was explained. Quantitative and qualitative features, features related to the content of the tweet and contextual features such as publishing time, user, follower count were explained. 
Data preparation is executed after the data was collected, upon concluding that the scrapped data is enough to run the analysis, then it was converted into a usable subset. Therefore, once a dataset was selected, it was checked for suspicious, missing, or ambiguous cases. This part was divided into context and content related features and data cleaning was performed for each part and new features were created for both sections. Among these, sentiment of the tweet, a content related feature, was created after a more detailed analysis than the others. This detailed analysis made a significant contribution to the project in terms of selecting the machine learning model to be used, comparing different preprocessing techniques, comparing the pretrained models with each other, and following a method for model evaluation that is as different as possible from those in the industry.

In modeling step, a selection od models are applied onto the cleaned dataset where all the features created at the end of data preparation are inserted into the model for prediction. Here, model training was done for two different predictions: binary classification and multiclass classification. Binary classification predicts whether a tweet will be retweeted or not and multiclass classification predicts how many retweets it will receive. In order to use resources and computational power as efficiently as possible, the models are sometimes trained on GPU using pycaret. Various techniques are applied in order to reach the highest recall rate as possible, including fine tuning, ensembling and blending models and SMOTE is used in order to prevent data leakage. 

For binary classification, highest recall is reached through blending ensembled models and for multiclass classification, the rate is highest for ensembled LightGBM. The success measures are given below.

Binary Classification:
![image](https://github.com/ardahiz/populartweets/assets/81987695/f2fe9069-af56-4899-9c98-0b35f2497c77)

Multiclass Classification:
![image](https://github.com/ardahiz/populartweets/assets/81987695/905f8dbd-e17e-45b5-99de-ebbe4a3e3712)


After deciding on the models to be used, these models were applied on the data set and the outputs were compared. In the evaluation part, both a comparison between the models and a comparison of the success metric obtained as a result of the steps within a model were executed. Last, resulting dataframe with predicted labels is deployed on reporting tool, PowerBI.
