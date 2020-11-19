
# The Problem with Mental Health in U.S. Policing

![Wapo 2020](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 8.39.42 PM.png)

![Mental Health Stats](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 10.30.00 PM.png)


## Introduction

"*Defund the Police*" is not a new rallying cry. From [The Guardian, June 2020](https://www.nytimes.com/2020/06/05/your-money/houses-prices-coronavirus.html), "For years, community groups have advocated for defunding law enforcement - taking money away from police and prisons - and reinvesting those funds in services." They estimate the movement has existed for **five years or more.** Perhaps stemming from the shooting of Michael Brown in Ferguson. [Timeline of Events in Ferguson, AP News, 2019](https://apnews.com/article/9aa32033692547699a3b61da8fd1fc62).

However, since the murder of George Floyd, the call to "Defund the Police" has increased in both frequency and volume. As quoted above, rarely does the movement advocate for a dismantling of police departments; rather, a reallocation of funds toward necessary services.

Shortly after the aforementioned shooting of Michael Brown and the emergence of "Defund the Police" to the mainstream, *The Washington Post* began tracking fatal police shootings in the U.S starting in 2015 ([Washington Post Database Overview](https://www.washingtonpost.com/graphics/investigations/police-shootings-database/?itid=lk_inline_manual_3)).

Perhaps one of the sharpest illustrations of a need to broaden, re-prioritize, defund, whatever one wants to call it, came with the death of Daniel Prude.

![daniel prude](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/daniel prude.png)


[On Daniel Prude, NYTimes, Oct 2020](https://www.washingtonpost.com/graphics/investigations/police-shootings-database/?itid=lk_inline_manual_3)

Daniel Prude, a 41 year old man in Rochester, NY, was hooded and restrained on the ground while suffering a mental episode. After an investigation into his death, the officers on the scene were cleared of any misconduct.

While Daniel Prude's name is not in *The Washington Post's* database, as he was not shot, his death is a tragic illustration of fatal force used against those suffering from a mental illness.

## Objectives

- Using *The Washington Post's* police shooting database, analyze the associated variables with police shootings involving a person suffering from a mental illness.
  - Per *The Washington Post's* breakdown of their dataset, their variable, "signs of mental illness," covers, **"News reports [that] have indicated the victim had a history of mental health issues, expressed suicidal intentions or was experiencing mental distress at the time of the shooting"**
- Build a comprehensive classification model.
- Present findings and solutions.

## Steps

1. Import necessary datasets (*Washington Post* and U.S. regions)
2. Clean and scrub the dataframes
3. Explore the datasets
4. Visualize and analyze relevant mental illness variables
5. Build and compare models

*For clarity and comprehension, this readme will focus primarily on exploration, visualization, and modeling.* The attached notebook follows a CRISP-DM approach.

### Questions, Analysis, and Visualizations

1. What categorical data provides the best insight into true/false signs of mental illness?
   1. How do these interact with each other?
   2. What can we learn from interactions?
2. Which continuous variables (primarily location and age data) provide the best insight into true/false signs of mental illness?
   1. How do these interact with each other?
   2. How do our continuous variables shine light on our categorical data?
2. How can we best visualize the categorical and continuous data to illustrate our findings?

#### Areas of Focus and Analysis
### **Gender**

![Gender/ MI/age](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 9.57.48 PM.png)


Comparing the two genders (*this dataset does not identify those who identify as non-binary or transgender*), 1/3 of women fatally shot by police were reported having/displaying signs of mental illness (MI signs)

![gender/MI/comparison ](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 7.34.33 PM.png)

Unlike men, who seem to peak (RE: MI signs) earlier, **earlier (20s-40s)**, there is a **consistent distribution of MI signs across age brackets for women.**

### **Race**

![race/MI](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 9.58.14 PM.png)



**Asian Americans** and **White (non-Hispanic)** Americans show a consistent trend, with the former peaking closer to middle age and above (>45).

![MI/age](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 7.34.12 PM.png)

**Black** and **Hispanic Americans** seem to have a higher rate of mental illness peaking at middle age (<40).

**Black women** and **White (non-Hispanic) women** are likelier than other ethnicities to display MI signs.

![race age gender](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 10.11.27 AM.png)

### **Location**

![Signs of mental illness by Division](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 9.57.12 PM.png)

The **Middle Atlantic Division** (New Jersey, New York, and Pennsylvania) contains the highest amount of fatalities with signs of mental illness.

**New England** (Conn., ME, MA, NH, RI, and VT) follows the Mid Atlantic Division in positive MI signs.

**East South Central** and the **Mountain** Divisions contain the lowest amount.  


*Are we looking at a population density issue? A higher confirmed rate in urban areas? A combination of the two?*

![mental illness division plot](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 7.37.26 PM.png)

New England’s suspected cases of mental illness peak into middle age (>40), while the Mountain and W. South Central divisions peak in the 20s and 30s.

The Mid Atlantic Division, perhaps due to its share of cases, has a steady line throughout age brackets.

![region gender](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 7.15.05 PM.png)


**We need to be aware of gender distribution among regions and divisions.**

### Modeling

![Model Overview](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.01.22 AM.png)

#### Where to Go?

Before diving into model building, a cursory overview of scores will give some insight into how our data is performing.

Due to the distribution of scores for LogReg, our RFC (random forest classifier), and our DTC (decision tree classifier), we'll start there. 

#### Methods of Model Analysis

**For each model, we'll use the following steps to build and analyze performance:**

1. Assign Test/Train Data to Model
2. Check Test/Train Performance
3. ROC/AUC scores
4. Confusion matrix
5. Investigate scores (Accuracy, Precision, F1, Recall)

**For our DTC and RFC models, we'll use a gridsearch to tune our results.**

#### LogReg

![ROC](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.02.16 AM.png)

- Checking our mean AUC score gives us: 
![AUC](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 11.05.56 AM.png)
	- This is not ideal - less than 20% better than a coin toss at a 50% AUC score. 

**Checking other metrics**

![CM lG](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.11.21 AM.png)

- Our data is giving us 708 + 37 correct predictions and 208 + 39 incorrect predictions. 

![logreg scores](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.04.15 AM.png)

- Our overall scores are decent, but the model is lacking in analysis for MI True.
- Accuracy for our **test set** is 75%.

#### Decision Tree Classifier

![DTC CM](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.11.42 AM.png)

- Our data is giving us 725 + 24 correct predictions and 221 + 22 incorrect predictions. *Slightly better than our LogReg.*

![DTC scores](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.05.32 AM.png)

- Our overall accuracy and averages are, again, *slightly better than our LogReg.*

- Accuracy for our **test set** is 76%.

#### Random Forest Classifier

-Based on our preliminary analysis, we'd expect our RFC to perform in a similar fashion as our DTC and LogReg. *This is not the case.*

![RFC CM](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.12.00 AM.png)

- Our data is giving us 504 + 145 correct predictions and 100 + 243 incorrect predictions. *Worse than our LogReg and DTC models*

![RFC scores](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-19 at 9.07.36 AM.png)

- Our RFC is doing a better job with MI True counts, but its averages and accuracy is much worse than the preceding models. 

## Model Conclusions and Further Work

### Final Accuracy Score
1. Logistic Regression
    - Accuracy: 75%
2. Decision Tree Classifier 
    - Accuracy: 76%
3. Random Forest Classifier 
    - Accuracy: 61%

### Our models need some help predicting MI True cases, but our overall accuracy scores for our LogReg and DTC models show promise. 

#### Future Steps for Modeling
1. Balance 
    - Prior to passing in "balanced_subsample" for our RFC's class weight, our confusion matrix was completely imbalanced. Passing "balanced" improved matters slightly, but did not help as much as the "balanced_subsample" assignment. 
    - Across the board, our precision and recall scores need to be improved for "true" instances of mental illness. 
2. ROC/AUC
    - Need to further explore ROC/AUC scores for DTC and RFC



## Business Deliverables
![Defund](/Users/conlp/FlatironWF/mod 3 project/final dataset and project selection/images/Screen Shot 2020-11-18 at 4.45.00 PM.png)

1. Reallocation of funds for crisis response should be funneled toward those most in need. Young men, women of all ages, Asian Americans, Black women. 
2. Different regions require different support strategies. Larger urban areas could benefit from a more nuanced crisis approach. 
3. More data is needed on: rural areas, gender identification (non-binary, transgender), funding for crisis calls, non-fatal injuries. 
    
