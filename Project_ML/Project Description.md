# Show/No-show Appointments
Asma Al Wazrah

## Abstract
Missed outpatient appointments are a common problem for clinics, and reducing this rate improves office efficiency, income, and utilize the time to help other patients. The goal of this project is to better understand which factors are most important in missing appointments, and how those factors relate to show/no show rate.

## Design
The data is provided by JoniHoppen from Kaggle, and presents a two-class status of not attending appointments, 'No' refers to attending, and 'Yes' refers to not attending. Classifying statuses accurately via machine learning models would Identify specific reasons why some patients miss outpatient appointments, which provide insight into developing targeted approaches to reducing their rates.

## Data
The dataset contains 110,527 rows with 14 columns of 12 features, 5 of which are categorical. Each row represents patient information, each column contains patient’s attributes described on the column Metadata.
The data set includes information about Patient ID, Appointment ID, Schedule Day, Appointment Day, Patient Age and gender, Neighbourhood, if the patient has (Scholarship, Hypertension, Diabetes, Alcoholism, Handicap)
if the patient receives SMS, and finally if the patient show or not.

## Algorithms

*Feature Engineering*
1. Extract a new feature (Difference, SD_week_no, AD_week_no), Difference indicates the difference between Schedule Date and Appointment date. In addition, SD_week_no and AD_week_no are the week number of the scheduled date and the Appointment date. 
2. Converting categorical feature (Neighborhood) to binary dummy variables.
3. Using MinMaxScaler on the numeric features (Age, Difference, SD_week_no, AD_week_no).

*Models*
  
Logistic regression, random forest classifiers, XGBoost, and Deep Neural network.

*Model Evaluation and Selection*
  
The entire training dataset of 110,527 records was split into 80/20 train vs. test. Predictions on the 20% test set were limited to the very end, so this split was only used and scores were seen just once.
Since it is classification problem, the official metric was classification rate (accuracy); however, the dataset is unbalanced. For this reason, the class weights were included to improve performance against F1 score and provide a more useful real-world application where classification of the minority class (functional needs repair) would be essential.

#BEST MODEL
**Final Deep NN test scores:** 93 features 
   - Accuracy 79.64%
   - precision 79.94%
   - recall 100%
   - F1 88.85%


## Tools
- Numpy and Pandas for data manipulation
- Scikit-learn and keras for modeling
- Matplotlib and Seaborn for plotting

## Communication
In addition to the slides and visuals presented, you can check the code <a href="https://github.com/AsmaAlWazrah/Projects/blob/master/Project_ML/Show%20-%20No%20show%20appointments.ipynb">here</a>

<img src="https://github.com/AsmaAlWazrah/Projects/blob/master/Project_ML/feature.png" width=1000>
