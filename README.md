# Analyzing-Social-Mobility-in-Baltimore-and-Washington-DC


## Background
A core pillar of American culture is the concept of the [American Dream](https://www.investopedia.com/terms/a/american-dream.asp), an belief that "anyone, regardless of where they were born or what class they were born into, can attain their own version of success in a society where upward mobility is possible for everyone. The American Dream is achieved through sacrifice, risk-taking, and hard work, rather than by chance."  While the concept of the American dream is supported by our countries laws and politicians, the harsh reality of the situation which many poor Americans face is a stark contrast.

This project seeks to provide an in depth statistical analysis of social mobility in two major cities, Baltimore, MD and Washington DC.

In Baltimore, a poverty striken city with high homicide rates, social mobility is extremely low.  Out of the 100 largest cities in the United States, [poor males growing up in Baltimore](https://afro.com/baltimore-ranks-lowest-in-upward-mobility-for-poor-boys/) have the least chance of becoming financially successful and achieving upward mobility.  In a nation founded on the principles that hard work and dedication will lead to a successful future, this fact shows that our idealist perception often differs substantially from reality.

In Washington DC a similar situation exists. [DC children in the lowest 25th percentile of incomes](https://www.dcfpi.org/all/economic-mobility-dc-lower-neighboring-counties/) have a substantially higher chance of having lower incomes as adults.  When poverty is systematic and lasting, we know that our nations ideals of social mobility and equal opportunity is failing us.

## Business Question
What can Baltimore and Washington, DC open data sources tell us about social mobility?

## Data Source
[Opportunity Atlas](https://www.opportunityatlas.org/): A free interactive tool that contains publicly available information on different social metrics.

Three different data sources were analyzed within tract ID numbers for each Baltimore City and Washignton DC: median household income, percentage of adults who stayed in same tract, and median income among adults who stayed in same tract.

#### Household Income
[Baltimore](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/Household%20Income%20Baltimore.csv)

[DC](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/Household%20Income%20DC.csv)
#### Percentage of adults who stayed in same tract
[Baltimore](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/%25%20Same%20Tract%20Baltimore.csv)

[DC](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/%25%20Same%20Tract%20Baltimore.csv)
#### Median income among adults who stayed in same tract
[Baltimore](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/income%20stay%20Baltimore.csv)

[DC](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/income%20stay%20DC.csv)

## Cleaning-Opportunity-Atlas-Data
The first step in data analysis is to clean Baltimore City and Washington DC publicly available data in order to track social mobility.

## Initial Data Cleaning Using Python
- The 6 different data sources were initially imported into google Colab using the code
pd.read_csv(urlofrawdata)
- Ensuring that the data sources were inputted properly is essential.  This uses the code df_(specificdataframe).head().
- Both the Baltimore City and the Washington, DC datasets contained datapoints that were neighboring towns and not within the city themselves. To clean this data to only include data containing Baltimore city code df_baltimorecitydata = df_baltimorecitydata[df_baltimorecitydata["Name"].str.contains("Baltimore")]. This process was then repeated for all Washington, DC data using contains("Washington, DC").
- In order to make the datasets easier to understand visually, it is essential to change the names of the columns within each dataset.  For example, to change the average incomeBaltimore dataset the code df_AvgIncomeBaltimore = df_AvgIncomeBaltimore.rename(columns={"Household_Income_rP_gP_pall":"Baltimore Median Income"}) was used.
- Finally, data merging was performed in which the 6 different data sources were combined in order to perform further analysis. This merging provides more in-depth coding, and all of the code used in this project can be found by clicking [this link.](https://colab.research.google.com/drive/1eCiJZyu8E-9K_7lrFo50r6eRZxm5udtH#scrollTo=jvpJPi71sAf7)

## Images of Cleaned Data
Below is 6 images of the cleaned data. This data now contains exclusively datapoints from within Baltimore City and Washington DC. Additionally, the columns within the data have been renamed and clarified. These 6 data sources are now optimally set up for further data analysis. For each data source, an example of the first 5 data points are displayed, and a description of the data including the mean, median, and standard deviation is shown below.

### Income among adults who stayed in the same tract
These two data sources measure the median income among adults who stay within the same tract. This data only measures an adult who was born in a specific tract within Baltimore City or Washington DC, and remained there for their entire lives.
#### Washington DC
![alt text](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/IncomeStayDCImage.png)
#### Baltimore
![alt text](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/IncomeStayBaltimoreImage.png)


### Median income in tract
These two data sources measure the median income among adults within a specific tract. This provides a good indicator of the relative wealth status of the residents in a specific area of each city.
#### Washington DC
![alt text](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/DCAvgIncomeImage.png)
#### Baltimore
![alt text](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/BaltimoreAvgIncomeImage.png)


### Percentage of adults who stay in the same tract
These two data sources measure the percentage of adults who stay within a specific tract. This provides an indicator of how many people grow up and move out of their neighborhood. This allows us to see the mobility rates among people within different neighborhoods.
#### Washington DC
![alt text](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/DCStayImage.png)
#### Baltimore
![alt text](https://github.com/AdamShmanske/Cleaning-Opportunity-Atlas-Data/blob/main/BaltimoreStayImage.png)

## What are the median household income of families and that of families who stayed in the same commuting zone?
![alt_text](https://github.com/AdamShmanske/Analyzing-Social-Mobility-in-Baltimore-and-Washington-DC/blob/main/average%20incomes.png)

## What does the distribution of tracts in Baltimore City look like based on the median income?
![alt_text](https://github.com/AdamShmanske/Analyzing-Social-Mobility-in-Baltimore-and-Washington-DC/blob/main/histogram%20Baltimore.png)

## What does the distribution of tracts in Washington, DC look like based on the median income?
![alt_text](https://github.com/AdamShmanske/Analyzing-Social-Mobility-in-Baltimore-and-Washington-DC/blob/main/histogram%20DC.png)

## Box Plots

### Baltimore vs DC Median Income
![alt_text](https://github.com/yoselassie99/Analyzing-Social-Mobility-in-Baltimore-and-DC-Using-Boxplots/blob/main/BaltimoreMedianIncomePlot.png)
- Highest Income is $75.5K
- Lowest Income is $16.0K
- Q1 Income is $21.7K
- Q3 Income is $36.4K
- The median is $27.5K

![alt_text](https://github.com/yoselassie99/Analyzing-Social-Mobility-in-Baltimore-and-DC-Using-Boxplots/blob/main/DCMedianIncomeBox.png)
- Highest Income is $83.5K
- Lowest Income is $19.2K
- Q1 Income is $25.6K
- Q3 Income is $40.0K
- The median is $30.3K

### Baltimore vs DC Stayed In Commuting Zone Income
![alt_text](https://github.com/yoselassie99/Analyzing-Social-Mobility-in-Baltimore-and-DC-Using-Boxplots/blob/main/BaltimoreIncomeStay.png)
- Maximum Income is $68.1K
- Minimum Income is $15.9K
- Q1 Income is $22.0K
- Q3 Income is $35.5K
- The median is $27.0K

![alt_text](https://github.com/yoselassie99/Analyzing-Social-Mobility-in-Baltimore-and-DC-Using-Boxplots/blob/main/DCIncomeStay.png)
- Highest Income is $73.6K
- Lowest Income is 20.7K
- Q1 Income is $26.5K
- Q3 Income is $37.7K
- The median is $30.6K

### Baltimore vs DC Percentage Stayed 
![alt_text](https://github.com/yoselassie99/Analyzing-Social-Mobility-in-Baltimore-and-DC-Using-Boxplots/blob/main/BaltimoreStayPercentage.png)
- Highest Percentage is 36.0%
- Lowest Percentage is 6.1%
- Q1 Percentage Stay is 18.2%
- Q3 Percentage Stay is 23.8%
- The median is 21.1%

![alt_text](https://github.com/yoselassie99/Analyzing-Social-Mobility-in-Baltimore-and-DC-Using-Boxplots/blob/main/DCStayPercentage.png)
- Highest Percentage is 37.6%
- Lowest Percentage is 5.0%
- Q1 Percentage is 17.7%
- Q3 Percentage is 26.5%
- The median is 22.6%

## Project Directions
A step by step description of the code needed to complete this project can be found [here](https://colab.research.google.com/drive/1eCiJZyu8E-9K_7lrFo50r6eRZxm5udtH#scrollTo=xb1ebKmGSEZH).  This allows replication of this project so that others can clean these same data sources and perform their own analysis on social mobility in these two cities.
