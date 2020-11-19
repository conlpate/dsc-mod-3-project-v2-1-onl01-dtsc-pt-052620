
# The Problem with Mental Health in U.S. Policing

![WAPO 2020](images/2020/11/wapo-2020.png)

![Mental Health Stats](images/2020/11/mental-health-stats.png)


## Introduction

"*Defund the Police*" is not a new rallying cry. From [The Guardian, June 2020](https://www.nytimes.com/2020/06/05/your-money/houses-prices-coronavirus.html), "For years, community groups have advocated for defunding law enforcement -taking money away from police and prisons- and reinvesting those funds in services." They estimate the movement has existed for **five years or more.** Perhaps stemming from the shooting of Michael Brown in Ferguson. [Timeline of Events in Ferguson, AP News, 2019](https://apnews.com/article/9aa32033692547699a3b61da8fd1fc62).

However, since the murder of George Floyd, the call to "Defund the Police" has increased in both frequency and volume. As quoted above, rarely does the movement advocate for a dismantling of police departments; rather, a reallocation of funds toward necessary services.

Shortly after the aforementioned shooting of Michael Brown and the emergence of "Defund the Police" to the mainstream, *The Washington Post* began tracking fatal police shootings in the U.S starting in 2015 ([Washington Post Database Overview](https://www.washingtonpost.com/graphics/investigations/police-shootings-database/?itid=lk_inline_manual_3)).

Perhaps one of the sharpest illustrations of a need to broaden, re-prioritize, defund, whatever one wants to call it, came with the death of Daniel Prude.

![Prude](images/2020/11/prude.png) 


[On Daniel Prude, NYTimes, Oct 2020](https://www.washingtonpost.com/graphics/investigations/police-shootings-database/?itid=lk_inline_manual_3)

Daniel Prude, a 41 year old man in Rochester, NY, was hooded and restrained on the ground while suffering a mental episode. After an investigation into his death, the officers on the scene were cleared of any misconduct.

While Daniel Prude's name is not in *The Washington Post's* database, as he was not shot, his death is a tragic illustration of fatal force used against those suffering from a mental illness.

## Objectives

- Using *The Washington Post's* police shooting database, analyze the associated variables with police shootings involving a person suffering from a mental illness.
  - Per *The Washington Post's* breakdown of their dataset, their variable, "signs of mental illness," covers, **"News reports [that] have indicated the victim had a history of mental health issues, expressed suicidal intentions or was experiencing mental distress at the time of the shooting"**
- Present findings and solutions.
- Build a comprehensive classification model.

## Steps

1. Import necessary datasets (*Washington Post* and U.S. regions)
2. Clean and scrub the dataframes
3. Explore the Datasets
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
1. **Gender**

![Gender/ MI/age](images/2020/11/gender-mi-age.png)

![gender/MI/comparison ](images/2020/11/gender-mi-comparison.png)

Comparing the two genders (*this dataset does not identify those who identify as non-binary or transgender*), 1/3 of women fatally shot by police were reported having/displaying signs of mental illness (MI signs)

Unlike men, who seem to peak (RE: MI signs) earlier, **earlier (20s-40s)**, there is a **consistent distribution of MI signs across age brackets for women.**

2. **Race**

![race/MI](images/2020/11/race-mi.png)

![MI/age](images/2020/11/mi-age.png)

**Asian Americans** and **White (non-Hispanic)** Americans show a consistent trend, with the former peaking closer to middle age and above (>45).

**Black** and **Hispanic Americans** seem to have a higher rate of mental illness peaking at middle age (<40).

![race gender age](images/2020/11/race-gender-age.png)

**Black women** and **White (non-Hispanic) women** are likelier than other ethnicities to display MI signs.

3. **Location**

![Signs of mental illness by Division](images/2020/11/signs-of-mental-illness-by-division.png)

The **Middle Atlantic Division** (New Jersey, New York, and Pennsylvania) contains the highest amount of fatalities with signs of mental illness.

**New England** (Conn., ME, MA, NH, RI, and VT) follows the Mid Atlantic Division in positive MI signs.

**East South Central** and the **Mountain** Divisions contain the lowest amount.  

*Are we looking at a population density issue? A higher confirmed rate in urban areas? A combination of the two?*

![MI age division](images/2020/11/mi-age-division.png)

New England’s suspected cases of mental illness peak into middle age (>40), while the Mountain and W. South Central divisions peak in the 20s and 30s.

The Mid Atlantic Division, perhaps due to its share of cases, has a steady line throughout age brackets.

### Modeling

![Model Overview](images/2020/11/model-overview.png)
