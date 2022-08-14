# Portugese Bank Data Details :- 

# bank client data:
#### 1 - age (numeric)
#### 2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
#### 3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
#### 4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
#### 5 - default: has credit in default? (categorical: 'no','yes','unknown')
#### 6 - housing: has housing loan? (categorical: 'no','yes','unknown')
#### 7 - loan: has personal loan? (categorical: 'no','yes','unknown')
# related with the last contact of the current campaign:
#### 8 - contact: contact communication type (categorical: 'cellular','telephone')
#### 9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
#### 10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
#### 11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
# other attributes:
#### 12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
#### 13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
#### 14 - previous: number of contacts performed before this campaign and for this client (numeric)
#### 15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')
# social and economic context attributes
#### 16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
#### 17 - cons.price.idx: consumer price index - monthly indicator (numeric)
#### 18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)
#### 19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
#### 20 - nr.employed: number of employees - quarterly indicator (numeric)

# Output variable (desired target):
#### 21 - y - has the client subscribed a term deposit? (binary: 'yes','no')


## <span style="color:blue">Steps followed to Analyse the Data :-</span>

#### <span style="color:green">1. Analyze the Data for null values and missing values to be filled.Null values are not seen the data.</span>
#### <span style="color:green">2. Analyze the Data for encoding, most of the data. Most of the columns are category type column. Category encoded the columns.</span>
#### <span style="color:green">3. Analyze the Data for imbalance. It is seen that the data is imbalanced. Balance the data for better model performance.</span>

## <span style="color:blue">Model Building Steps [Logistic Regression, KNN, Decision Tree Classifier, SVC]:-</span>

#### <span style="color:green">1. The first 7 columns are used as features for the model. The rest of the columns are dropped.</span>
#### <span style="color:green">2. Split the data into Train and Test data with 30% data going into Test. Used the balanced data for model building</span>
#### <span style="color:green">3. Plot the Sequential Feature Selection to see the gain with the selected features for each of the model.</span>
#### <span style="color:green">4. Collect the model metrics viz. score, fit time etc. into a data frame and plot it to see the trend.</span>

## <span style="color:blue">Conclusion from Basic Model</span>

#### <span style="color:green">The Basic model is seen to have low performance. KNN being the best performing model in terms of accuracy and Decision Tree being the best performing in terms of training time</span>

## <span style="color:blue">Model Testing and Cross Validation</span>

#### <span style="color:green">Use a cross validation technique to test the model and see if there are any improvements.</span>
#### <span style="color:green">Default params have been used.</span>
#### <span style="color:green">Record the model metrics in a data frame and plot to see the comparison on fit time and accuracy.</span>

## <span style="color:blue">Use a cross validation technique to test the model.</span>

#### <span style="color:green">The basic cross validation has had no effect on the model performance, the time taken by the model has increased in some cases but the performance hasn't seen any improvement</span>

## <span style="color:blue">Model Improvement.</span>

#### <span style="color:green">1. Following Steps have been taken in attempt to improve the model performance.</span>
#### <span style="color:green">2. Add Additional features to the data</span>
#### <span style="color:green">3. Balance the class after adding additional features</span>
#### <span style="color:green">4. Encode the new features using category encoder</span>
#### <span style="color:green">5. Tune the Hyper parameters on each of the model</span>

## <span style="color:blue">Conclusions from Model Improvement Attempts</span>

#### <span style="color:green">Adding additional features has improved the model performance though has impacted the fit time of the model</span>
#### <span style="color:green">Hyper parameter tuning has improved the model performance though has impacted the fit time of the model</span>
#### <span style="color:green">Model improvement has shown significant improvement in the model performance</span>
