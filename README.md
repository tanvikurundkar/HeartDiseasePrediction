# Heart Disease Prediction
Using logistic regression, support vector machine and KNN models to predict the likelyhood of heart disease.
## Description of Dataset
### Labels
  - No heart disease=0
  - Heart Disease=1
### Features
  - Age: age of the patient [years]
  - Sex: sex of the patient 
     - M: Male 
     - F: Female
  - ChestPainType:  
     - TA: Typical Angina 
     - ATA: Atypical Angina
     - NAP: Non-Anginal Pain
     - ASY: Asymptomatic
  - RestingBP: resting blood pressure [mm Hg]
  - Cholesterol: serum cholesterol [mm/dl]
  - FastingBS: fasting blood sugar 
     - 1: if FastingBS > 120 mg/dl
     - 0: otherwise
  - RestingECG: resting electrocardiogram results 
     - Normal: Normal
     - ST: having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV) 
     - LVH: showing probable or definite left ventricular hypertrophy by Estes' criteria
  - MaxHR: maximum heart rate achieved [Numeric value between 60 and 202]
  - ExerciseAngina: exercise-induced angina 
     - Y: Yes 
     - N: No
  - Oldpeak: oldpeak = ST [Numeric value measured in depression]
  - ST_Slope: the slope of the peak exercise ST segment 
     - Up: upsloping 
     - Flat: flat 
     - Down: downsloping
  - HeartDisease: output class 
     - 1: heart disease
     - 0: Normal
     
## Methodology
We used the Heart Failure Prediction Dataset from Kaggle

We plotted various barplots, box plots, scatterplots, histograms, etc. comparing the respective parameters with heart disease to get an insight into the data we are working with.We then pre-processed the data which involved removing null values, outliers and relatively unimportant values in order to narrow it down and ensure our results are more accurate. No correlated features existed, therefore further modification was not required. Additionally, we standardized features(converting all data to uniform units) and split data into 80% training and 20% testing for fitting the AI models.
## Preprocessing
- Removing outliers : IQR based filtering - removing values outside the middle 50%
- 3 standard deviations from the mean value
- convertion of categorical features to numerical ones to include all the features while fitting the models
- Random forest model : feature importance
   - The relatively unimportant ones = FastingBS, sex, RestingECG  columns(lower imp than 0.05 and hence were removed from the dataset) 

## Modeling
 - Logistic Regression
   - Accuracy: 0.8742857142857143
   - F1 score: 0.87
   - AUC score: ROC AUC=0.939
 - KNN
   - Accuracy: 0.7663043478260869
   - F1 score: 0.77
   - AUC score: ROC AUC=0.839
 - SVM
   -Accuracy:  0.7608695652173914
   - F1 score: 0.76
   - AUC score: ROC AUC=0.863

## Model Implications
Can be modified to predict some other parameter of patient data(instead of heart disease).
## Limitations
Simpson's paradox:  a patient with typical angina would be more likely to suffer from heart disease than those with atypical angina, non-anginal pain or asymptomatic pain. Whereas as per this dataset, the most positive cases are asymptomatic and the least are typical angina which is quite controversial. 
Further investigation as a next step will lead to finding this hidden factor and solving this paradox.  
Next steps: The current model can be enhanced with additional risk factors. Following features should also be considered:
 - Nicotine usage
 - alcohol usage
 - Diabetes
 - BMI
 - country/region of residence
 - results of fluoroscopy of the patient
 
 ## Conclusion
 We can conclude that heart disease is predictable by AI. The accuracy of the models is fairly high and is proved to be quite consistent and efficient.

Do look into my research paper at: https://docs.google.com/document/d/1OdKvWvMVffzgKq9OgW19C4OqRku8r3ziwiMIgFvjLUc/edit?usp=sharing



