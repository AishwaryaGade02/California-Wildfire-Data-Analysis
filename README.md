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

1. The majority of wildfires are caused by human activities.

2. Shasta County experienced the highest number of wildfires.

3. The highest number of wildfires occurred in October 2018.

4. The wildfire with the most financial loss occurred in 2019 in Butte County.

5. The largest wildfire (by area burned) occurred in Shasta County in 2016 due to lightning.

6. No strong correlation was observed between the numerical variables in the dataset.
### New Feature Creation and Correlation Analysis <br/>
To explore whether larger counties experience more human-caused wildfires, the following approach was used:

County population data was scraped from Wikipedia using BeautifulSoup.

The correlation between county population and wildfires caused by human activities was calculated.

The "Cause" column was encoded to extract human-caused wildfires.

Correlation coefficient: -0.1497, indicating no significant relationship between county population and human-caused wildfires.

### Hypothesis Testing <br/>
From visualization, it appeared that smaller counties may experience more wildfires than larger counties. To validate this, hypothesis testing was performed:

#### Hypotheses:

**Null Hypothesis (H₀)**: The number of wildfires in small and large counties is the same.

**Alternative Hypothesis (H₁)**: Smaller counties experience more wildfires than larger counties.

#### Methodology:

Defining Small and Large Counties:

The median county population was used as a threshold.

Counties below the median were classified as small.

Counties above the median were classified as large.

#### Grouping Wildfire Causes:

Added new columns indicating wildfire count per cause in each county.

Mann-Whitney U Test (since data was not normally distributed) was used to compare wildfire counts between small and large counties.

#### Test Results:

U-statistic: 1386.0

p-value: 0.1653

#### Conclusion:

Since p-value > 0.05, we fail to reject the null hypothesis. This indicates that there is no statistically significant difference in the number of wildfires between small and large counties.

#### Summary
This project conducted an analysis of the California Wildfire Dataset, uncovering insights into wildfire causes, locations, and financial impact. Although visualization suggested that smaller counties might experience more wildfires, statistical analysis did not confirm this hypothesis.
