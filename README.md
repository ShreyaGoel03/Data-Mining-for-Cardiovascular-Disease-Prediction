# Data-Mining-for-Cardiovascular-Disease-Prediction
## Introduction
<p align = "justify"> 
Cardiovascular diseases (CVD’s) is a set of high-risk diseases, which affects the heart and blood vessels of the body. CVD is caused due to high blood pressure, high cholesterol, alcohol, smoking, etc. It can moreover affect other organs in the body such as the mind, kidneys and eyes. Sometimes
when it is not cured on time, it becomes the leading cause of death. </p>
<p align = "justify">
Presently, the Medical Diagnosis System is playing an essential role in diagnosis and treatment. The project focuses on predicting the risk of Cardiovascular disease among patients using Machine Learning and Deep Learning techniques.
The information is being extracted from the clinical records of the patient collected using Data Mining. This system’s automation will help the physicians for a fast and better diagnosis in the future with a reduction in costs. It also stresses
Data Analysis, which plays a vital role in the medical field’s progress by suggesting the proper treatment according to the patient’s characteristics.</p> 

<p align = "justify">
Various lifestyle factors are considered, such as age, blood pressure, weight, height, cholesterol, alcohol, activity, and many more, which play a significant role in the high risk of Cardiovascular Disease. Hence, a sound prediction system is required for cardiovascular disease so that people can stay more healthy and safe. The main aim is to determine the individuals at higher risk of developing Cardio Vascular disease at an earlier stage to avoid premature deaths.</p> <br/>

## Data Understanding
<p align = "justify">
The Cardiovascular Disease dataset is obtained from Kaggle [1], in which the data was collected at the moment of medical examination. The data does not contain any directly identifiable information. The dataset consists of 70,000 records of patient data, 11 features, and one target variable, which gives the presence or absence of cardiovascular disease in the form of 1 or 0, respectively. All 12 features are broadly categorized into three categories:<br/>
&nbsp;• Objective: factual information;<br/>
&nbsp;• Examination: results of medical analysis;<br/>
&nbsp;• Subjective: the patient gave information.<br/></p>
<img src="https://user-images.githubusercontent.com/43794593/154681492-29c4071f-e905-454c-879b-25b095abcbfa.png" width=30% height=30%> 

## Data Preprocessing
<p align = "justify"> The first step is to preprocess the data, which is performed before training and testing the model. The different preprocessing approaches have been applied based on the input data as follows:</p> 

### Data Cleaning
<p align = "justify"> The irrelevant and missing parts from the data was cleaned. Data must be cleaned by filling any missing values, identifying the noisy data or outliers, and resolving inconsistencies.</p> 
<p align = "justify">
1. <b> Removal of Duplicate Data</b>: The duplicate rows were dropped from the data. There were 48 duplicate rows present in the data.<br/>
2. <b> Missing Values or Inconsistencies</b> : There was no missing value found in the data and any discrepancies in the values.<br/>
3. <b> Outliers Removal</b> : As the figure shows, the extreme values deviating from other observations present in the data. Also, The outliers values are not possible in the real world. The Interquartile Range method was used to remove outliers from columns - ap_lo, ap_hi, weight and height. The extreme values were detected and removed based on the interquartile ranges.<br/></p>
<img src="https://user-images.githubusercontent.com/43794593/154682885-993ce9fa-9438-43a3-b270-55da29675ec2.png" width=30% height=30%> 

### Data Transformation
<p align = "justify"> The data needs to be consolidated in the form which is relevant for modelling.</p> 
<p align = "justify">
&nbsp;1. The age column was converted into years by dividing the values with 365.24.<br/>
&nbsp;2. The weight and height columns were integrated into BMI Index as weight and height are highly correlated. A new column bmi was added to the data.<br/>

After preprocessing, there were 66775 patients whose records were kept for consideration.</p>

## Data Analysis
<p align = "justify"> For the analysis, data visualization is done to get a better understanding of data. The class distribution of target variable cardio is visualized by a bar plot, where around 50% (35004) users belong to the positive class, i.e., "1." In comparison, 49.9% (34972) users belong to the negative class, i.e., "0," which implies that there is no class imbalance in cardio distribution. Age is converted into years, and cardiovascular disease risk is analyzed among various age groups, in the Figure below. It shows that people having age more than 55 are vulnerable to cardiovascular disease.</p>
<img src="https://user-images.githubusercontent.com/43794593/154690279-453cc705-b37e-46ef-87de-b843dc8ea298.png" width=30% height=30% /> 
<p align = "justify"> The histograms analyze Data distribution for all available attributes in Figure 5 where the bar represents the range of count of patients for every feature obtained after preprocessing. </p>
<img src="https://user-images.githubusercontent.com/43794593/154693257-25db5564-6dfe-4ca9-a24d-cfefc0990667.png" width=30% height=30% />
<p align = "justify"> The Box plot with the features gender, alcohol, and BMI is shown in the figure below in which it is observed that Alcoholic women have a higher Risk of CVD than Alcoholic men. The rate of Having Cardiovascular disease based on Alcohol, Gender, Glucose, Cholesterol Level, Smoking, and Physical Activity, are shown by a pie chart in the figure. The rate of not having a cardiovascular disease based on variables mentioned above is also shown in figure. On Comparing the plots, It is obtained that Cardiovascular diseases are not much affected by gender, while it majorly depends on body Glucose level and Cholesterol level.</p>
<p float="left">
<img src="https://user-images.githubusercontent.com/43794593/154693401-1600debb-28c2-40bd-ac7d-392a8d8284e3.png" width=30% height=30% >   <img src="https://user-images.githubusercontent.com/43794593/154693407-6110b19c-67e3-4459-8a11-61f96a9382bf.png" width=40% height=40% /></p>

<p align = "justify"> A Heatmap in figure displays the correlation between features and also with target variable. The feature with higher correlation with target variable are given more importance than features correlated with independent variables. The figure also shows that ap_hi and ap_lo are highly correlated with the target variable, and gender is the least correlated variable with target. Also, height, glucose, smoke have less amount of a correlation with the target variable cardio. </p>
<img src="https://user-images.githubusercontent.com/43794593/154693460-19c86750-de4a-4935-bf20-681044e54f1b.png" width=30% height=30%/>

## Methodologies

<p align = "justify"> Various models have been implemented including Logistic Regression (LR), Support Vector Machine (SVM), k Nearest Neighbour (k-NN), Naive Bayes (NB), Decision Tree (DT), Random Forest (RF), Gradient Boosted Tree (GBT), Light Gradient Boosted Tree(LGBM), XGBoosting (XGB) and lastly CatBoost (CB) for the baseline implementation. All experiments were performed after a 70:30 training and testing split as it yielded a decent amount of testing data to capture most of the variance in the data. For the experiment 1, all attributes were considered. For the experiment 2, attributes with less feature importance which includes gender, gluc, alco, smoke and active were removed as shown in Figure.</p>
<img src="https://user-images.githubusercontent.com/43794593/154694314-11f74c50-f2a6-4db8-9078-edc5ef24242f.png" width=30% height=30%/>

## Evaluations and Conclusion
<p align = "justify"> or evaluation, receiver operating characteristic curve (ROC curve) was also made as shown in the figure. e can observe that the in traditional ML techniques, we got accuracy of around 72% whereas in boosting algorithms and neural network, we got 73% accuracy (a minor improvement). However, accuracy is not a reliable measure in healthcare domain due to a large difference in true negatives and false positives. The number of false positives must be minimized as much as possible as the impact due to false pitives is much more than impact due to true negatives.</p>

<p align = "justify"> Hence, sensitivity and precision are much better measure than accuracy and specificity. Boosting algorithms tend to work better than traditional machine learning algorithms. In conclusion, it was observed that machine learning models were able to achieve around 70 percent score in balanced dataset. Overall, it can be noted that boosting algorithms and neural network will perform better. Some achieved decent score also hence, viable to use in prediction of CVD’s.</p>
<img src="https://user-images.githubusercontent.com/43794593/154694323-4b22b120-2ff8-4553-95e2-a83817040c83.png" width=40% height=40%/>


#### Team Members:<br/>
1. Shreya Goel
2. Richa Dwivedi
3. Pruthivi Raj Behera






