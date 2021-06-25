# Medical Cost Prediction Analytic

This is the data set on the medical cost treatment of different patients. In this project, there is no medical history data. However, it consists information of age, region, bmi, gender, smoker or non smoker and charges which can be analysed and to develop a model to predict medical cost charges. 

## Code and Resources Used

**Python Version:** 3.7 <br>
**Packages:** numpy, pandas, seaborn, matplotlib, sklearn <br>
**IDE:** Google Colab <br> 
**Dataset:** https://www.kaggle.com/mirichoi0218/insurance

## Data Gathering

The dataset used in this project can be downloaded from Kaggle (link as shown above). It is about medical cost expenses. This dataset consist of 1338 rows and 7 features. The information of the dataset includes: <br>
* Demograhpic info - age, gender, bmi
* Number of children for a patient
* Smoker or Non smoker
* Origin of the patient
* Charges (medical cost expenses)

## EDA

To understand the patterns and values of the data by using different types of visualizations. <br>

#### Heatmap
![](/images/1.ICP_heatmap.png)

Based on the heatmap, it can be seen that smoker, age, bmi and children features are with positive association with charges feature, i.e, the higher the values for smoker, age, bmi and children features, the higher the charges value. <br> We will explore more on the smoker, age and bmi.

#### Age vs Charges
![](/images/2.ICP_age_vs_charges.png)

Finding shows that increase in the age will also increase the medical charges for both smokers and non smokers. 

#### Patient Distribution
![](/images/3.ICP_patient_count_region.png)

Southeas region is with the highest number of Obese patient and medical cost is also the highest among the 4 regions. 

#### Comparison on Smoker and Non Smoker Based on Age Group
![](/images/4.ICP_patient_age_cost.png)

Medical cost for Non Smoker <br>
Young Adult (431) - 4738.48 <br>
Middle Age (455) - 9765.08 <br>
Senior (176) - 14087.58 <br>

Medical cost for Smoker <br>
Young Adult (116) - 28095.82 <br>
Middle Age (118) - 33407.87 <br>
Senior (40) - 39513.00 <br>

In general, medical cost of smokers are higher for Young Adult, Middle Age and Senior groups as compared with non smokers. It should be noted that the number of smokers is far lesser than non smokers for each of the age group.

#### Comparison on Smoker and Non Smoker Based on BMI Category
![](/images/5.ICP_patient_bmi_cost.png)

Medical cost for Non Smoker <br>
Overweight (301) - 8320.95 <br>
Obese (574) - 8832.88 <br>
Normal Weight (172) - 7599.64 <br>
Uder Weight (15) - 5532.99 <br>

Medical cost for Smoker <br>
Overweight (72) - 22379.03 <br>
Obese (147) - 41355.87 <br>
Normal Weight (50) - 19942.22 <br>
Uder Weight (5) - 18809.82 <br>

In general, medical cost (on average) of smokers are higher for Obese is the highest, followed by Overweight, Normal Weight and Under Weight. It should be noted that the number of smokers is far lesser than non smokers for each of the BMI category.

#### Medical Charges vs BMI Category, with Different Age Groups
![](/images/6.ICP_patient_bmiCat_cost.png)
![](/images/7.ICP_patient_ageCat_cost.png)

The finding shows that most of the medical costs for smokers are higher than non smoker, given the same bmi. <br> Also, smokers with Obese are required to spend more on medical cost as compared to smokers with Overweight, Normal Weight and Under Weight. <br>
Also, it is obvious that smokers with Obese are needed to spend more on medical cost as compared to Overweight, Normal weight and under weight smokers, regardless to Young Adult, Middle Age and Senior age groups.

#### Age, BMI vs Charges with Different Regions
![](/images/8.ICP_age_vs_charges.png)
![](/images/9.ICP_bmi_vs_charges.png)

It is found that region does not show any significant insight. This is also relfected the finding from the heatmap where there is no strong association between regions and charges.

#### Charges Distribution for Smoker and Non Smoker vs Number of Children
![](/images/10.ICP_child_vs_charges.png)

#### Charges Distribution for Smoker and Non Smoker vs Region
![](/images/11.ICP_region_vs_charges.png)

#### Charges Distribution for Smoker and Non Smoker vs Sex
![](/images/12.ICP_sex_vs_charges.png)

## Model Building

The input features identified for the model training are age, bmi and smoker. Charges will be the output (target).
**train_test_split** from **sklearn.model_selection** is used to separat the dataset into training and testing set of data. In this project, 80% of the dataset is used as training set and the remaining 20% is used as testing set. <br>
The prediction model selected are **LinearRegression** and **RandomForestRegressor**

## Performane Evaluation

Coefficients [age,bmi and encoded_smoker] and Intercept produced by the model. <br>

Coefficients: [  259.83736925   322.61300185 23827.39344353]<br>
Intercept: -11691.638457668056 <br>

From the coefficient, it can be seen that encoded_smoker is with the highest weight in determining the medical cost (charges) of a patient. <br> 

Based on the result, the performance of <br> 
Linear Regression is with the score of 74.51%. <br>
Random Forest Regressor is with the score of 97.23%.
