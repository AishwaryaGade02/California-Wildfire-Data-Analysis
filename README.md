## Data Analysis on California Wildfire Dataset
The goal of this project is to conduct exploratory data analysis, correlation analysis and descriptive statistics on California wildfire dataset. The data is taken from kaggle.
The dataset consists information from 2014 to 2025. The data contains following variables
### Feature Description
Incident ID: It is the unique identifier for all the wildfire incidents <br/>
Date: Date on which incident happened <br/>
Location: Place at where the wildfire took place <br/>
Area_Burned(Acres): Area that is burnt in acres <br/>
Homes_Destroyed: No.of homes that got destroyed <br/>
Businesses_Destroyed: No.of business that got destroyed <br/>
Vehicles_Destroyed: No.of Vehicles that got destroyed <br/>
Injuries: No.of people who got injuried <br/>
Fatalities: No.of fatalities that got damaged <br/>
Estimated_Financial_Loss (Million $): Financial loss in millions <br/>
Cause: Cause of wild fire <br/>
Year: When the wild fire happened <br/>

### Findings from Exploratory Data Analysis <br/>
1. Most of the wildfires are caused by Human Activities
2. Most number of wild fires occured in Shasta County
3. There are most number of wildfires in October 2018 in California
4. The wildfire that caused most financial loss happened in 2019 in Butte County
5. The wildfire that caused damage to most of the land happened in Shasta County in 2016 caused due to lightening
6. There is no strong correlation between the variables

### New Feature Creation and Correlation Analysis <br/>
I wanted to explore if there is any linear relation between the size of the county and the cause of the wildfire. Assumption of this analysis is that the wildfire caused in large counties
is more due to Human cause. Hence I extracted the population of all the counties that are present in the dataset from wikipedia using BeautifulSoup. After extracting the 
population I calculated the correlation between population of county and wildfires caused by Human Activities. The cause column in the dataset is encoded to get wildfires caused
by Humans column. The correlation between population of county and wildfires caused by Human Activities is -0.1497, which suggests that there is no correlation between population 
of the county and the wildfires caused by Human Activities

### Hypothesis Testing <br/>
From the data visualization, it is observed that the small counties are having more wildfires than the larger ones. Hence I wanted to test this hypothesis. First we need to distinquish
between small and large counties. To do that, I calculated the median of population of the counties. If any population is less than the median then that county is treated as small county
and if any county's population is greater than the median values then that county is treated as big county. Then I added new columns which gives information about the count of 
each cause in that particular county. I created two dataframes small_counties and large_counties including the count of causes. As the data I have is not normally distributed, I
used Mann-Whitney U test to test the hypothesis <br/>

Null Hypothesis: The number of wildfires in small and large counties is the same
Alternate Hypothesis: Smaller counties have more wildfires than larger counties <br/>

The result of the test is given as below<br/>
U-statistic: 1386.0 <br/>
p-value: 0.16525263394068768 <br/>

As p-value > 0.05, we fail to reject the null hypothesis. Hence we say that the number of wildfires in small and large counties is same
