# Kickstarting with Excel

## Overview of Project
    The project looks into the sample Kickstarter data that would allow our client (Louise) to determine the likelihood of successfully raising her Kickstarter goal to finance the development of her play. 

### Purpose
    The purpose of the project is to analyze the likelihood of success for a Kickstarter campaign based on:  
        1. Country
        2. Category
        3. Subcategory
        4. Year 
        5. Month
        6. Monetary Goal
    These dimensions provide an opportunity to look deeper by segmentating the data and provide better expectations based on historical data trends.

## Analysis and Challenges
    The data provided good opportunities to segment the data across various dimensions.
    Analysis:
        1. Based on the context around the time frame and the rate the donations are filling towards the goal, one would assume Louise's play has a lower goal (less than $15000, greater than 50% chance of success), thus increasing the likelihood of successfully raising her goal.
        2. The additional categories and data transformations were done in the Excel spreadsheet from the source
                3. Link to spreadsheet:
            [Kickstarter_Challenge]https://github.com/plymburner/DataBootcamp/blob/main/Kickstarter_Challenge.xlsx
    Challenges:
        1. One dimension, dates were stored as a Unix Timestamp and needed to be converted to a date for further analysis based on Year and Month for rendering into the Outcomes Based on Launch Date.
        2. Outliers in the data cause skew when looking at the data in a purely statistical approach and the those outliers were plain to see when using box plots.
        3. Limited data size may result in the data not providing accurate estimations based on the Central Limit Theorm.
        4. Creating bins of inconsistent sizes, when looking into the goal amounts and presented the opportunity to automate the bin size for segmenting the goal totals for the data. Based on specifications for the project a manual process was established to group the data.

### Analysis of Outcomes Based on Launch Date
    Outcomes:
        1. Successful
            - Successful campaigns tended to result in more often throughout the year, yet during the late spring and summer months tended to have higher success rates with the increased frequency of new campaigns 
        2. Failed
            - Failed campaigns follow similar trend to the successful campaigns, at a lower magnitude.
            - With the lower magnitude, there seems to be less seasonality in the results, which would potentially be attributed to another factor.
        3. Canceled
            - The cancelation rate appears to be consistent throughout the year, excluding the gap in October
        4. Overall
            - The holiday season (November, December) showed the lowest frequency of campaigns as well as much lower frequencies of successful campaigns, which could be a result of people not seeing the campaigns or the money people have at that time being spent elsewhere.
    Link to Visual:
        [Theater_Outcomes_vs_Launch]https://github.com/plymburner/resources/blob/main/Theater_Outcomes_vs_Launch.png

### Analysis of Outcomes Based on Goals
    Outcomes:
        1. Successful
            - There are two high probability goal amount areas (0 to 19999 and 35000 to 44999)
            - The percentage may be positive in the bins containing 35000 to 44999, yet the low number of occurances could result the percentage changing, potentially dramatically.
        2. Failed
            - The percentage of failure increases at a higher rate once the campaign goal reaches 20000 to 24999, which shows how increasingly difficult it is to successfully reach the goal, additionally that's the bin with the lowest double digit total count of campaigns.
        3. Canceled
            - There were no canceled Kickstarter campaigns for that subcategory
        4. Overall
            - With the use of a percentage value, there is an inverse relationship between the Successful and Failed outcomes (i.e. one outcome goes up, the other comes down)
            - Since this is a small subset of the data towards the higher goal bins, the percentage could change dramatically as more campaigns occur. 
            - With the distribution with a long tail (Poisson Distribution), the statisctics would need to be calculated differently
    Link to Visual:
        [Outcomes_vs_Goals]https://github.com/plymburner/resources/blob/main/Outcomes_vs_Goals.png

### Challenges and Difficulties Encountered
    1. Limited Sample Data
        - The sample size becomes increasingly smaller as the data is drilled through in to sub categories and dimensions.
        - The decreasingly smaller number of occurances, makes analysis results towards the tails less reliable.
        - The number of data columns was limited and may not contain all dimensions that may provide additional insights into successful campaign prediction
    2. Key Influencers
        - The project only looked at single factors at a time, when there may be multiple factors at play making the reliance on a few factors less impactful than a more inclusive multi-factor analysis

## Results

    - What are two conclusions you can draw about the Outcomes based on Launch Date?
        1. Late Spring into early Summer present the best opportunity to launch a campaign. The number of successful campaigns increase at that time while the failed campaigns do not see the proportionate increase that successful ones do.
        2. The holiday (Christmas) is the weakest time of year with fewer campaigns starting and a higher proportion of failed outcomes.

    - What can you conclude about the Outcomes based on Goals?
        1. Campaigns with goals less than 15000 has the best chance for successful outcomes (50% or higher).
        2. The higher goals are more difficult to determine because of their tendency to have fewer occurances.

    - What are some limitations of this dataset?
        1. There isn't a lot of defintion to the data with limited attributes for us to evaluate and determine contributing factors for successful campaigns
        2. The small sample size makes reliable conclusions more difficult when the number of occurances reaches single digits because the derivived metrics can dramatically with the addition of additional occurances.
        3. Not all perspectives of the data are normally distributed and alternative methods would be needed for summary statistics i.e. Occurance counts of goal amounts by dollar range bin being skewed to the right.

    - What are some other possible tables and/or graphs that we could create?
        1. Graphs
            - Stacked bar for Outcomes based on Goals to represent the data in a format that will show the data based on proportion of a whole.
            - Two axis charts for the comparison of multiple factors to better determine key drivers of a successful campaign.
