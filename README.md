# An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter data to uncover trends for the purpose of advising a hopeful playright to start her campaign.

## Overview of Project

My client, Louise, is a playwright looking to crowdfund for her play, Fever. With an estimation of a $10,000 budget, she would like to know what specific elements to include in her crowdfunding campaign in order to yield successful results. As such, historical data on crowdfunding is pulled and to be analyzed in this project, with the goal of generating valuable insights for Louise. Throughout the analysis, it will be particularly pertinent to focus on campaigns for theater as Fever falls in such a category.

### Purpose

The purpose of this analysis project is to isolate data of theater campaigns, visualize using charts how various factors contribute to campaign outcomes, and come up with insights based on the data. For this project, using Excel best serves our purpose.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

Since the given raw data contains an excess of information that does not pertain to Louise (e.g. campaigns for mobile games, food trucks etc.), it will be useful to create a pivot table so that we can view and filter data as we please. To create a pivot table that visualizes theater outcomes by launch date, refer to the figure of how the different variables are organized for the table. First, we want to only view theater outcomes so there should be a filter for the parent category. Then we would like to filter by year if needed. For the rows ,which correspond to the x-axis of the chart, we are interested in what month the launch date was (and the default setting separates based on month). Finally, we are interested in how many campaigns were successful, failed, or canceled and viewing that in the columns and values (which corresponds to the y-axis) gives us our final table and chart.

### Analysis of Outcomes Based on Goals

To chart goal value as the independent variable (i.e. the x-axis) will require us to assign numerical ranges in $5000 increments. This will allow us to group together data in a logical manner. In order to make Excel count the number of plays that succeed, fail, or get canceled based on its goal value, we use the COUNTIFS function. The following example is for counting the number of successful play campaign outcomes for those with goal of $0 to $999:

=COUNTIFS(Kickstarter!$D:$D,">=0",Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")

Excel will count the campaign if all of the above conditions are met, as in the D column value (goal) is a value between $0 and $999, the outcome is successful, and the sub-category is classified as play. A series of these COUNTIFS functions can allow us to create a table of the number of successful, failed, and canceled campaigns based on the goal ranges. We also want to visualize this number count as a percentage of the total amount of projects within that goal range. To do that, a new column (E) is created to calculate the number of total projects, using the =SUM(B__:D__) function with blanks containing the row number. This sums the number of projects in each outcome category to get a total.

To calculate the percentage for successful campaigns, a new column (F) is created and formatted to present % values with 1 decimal place. The function used for these cells would be =B__/E__, with the blanks containing the row number. This allows the number of successful projects to be divided by number of total project, yielding percentage. Similar formula is used for the failed and canceled campaigns, although with different columns involved. Once the table is complete, a line graph is created to visualize the data. 


### Challenges and Difficulties Encountered

The only challenge I encountered was during the COUNTIFS portion of the Outcomes vs. Goals analysis. Since there were repetitive copy-and-pasting of the formula with only certain parts changed to fit the goal range, I made a typo in one of the formulas which led to a different graph than what was given. If I was not provided with the visual of what the graph should end up looking like, I would have analyzed an inaccurate chart. Since real-life data analysis will not provide an answer beforehand, I learned the importance of proofreading each formula meticulously during analysis.


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

First, when looking at the graph for successful outcomes, it is clear that setting the launch date during the months of May and July can yield a higher likelihood of a successful campaign. This is seen by the increase (of % of plays) seen in the "successful" category compared to the other "failed" and "canceled" categories during those months.

That being said, the second conclusion that can be drawn from this data is that campaigns that fail likely have other factor(s) contributing to their failure aside from launch date. This is shown by the fairly consistent failure rate through all the months, indicated by the "failed" line graph with values oscillating around the 40% mark. This seems to suggest that if the play was predisposed to failing by some other deciding factor, launching in peak months will not be enough to save the campaign if other factors are not considered. Therefore, further analysis is required to determine what those other deciding factor(s) may be. 

Overall, for Louise, she should note that the launch date for her campaign should occur sometime within the summer months for greater chances of success.


- What can you conclude about the Outcomes based on Goals?

According to the play campaigns analyzed, 50% or greater than 50% of them are successful if the goal amount of the campaigns lies from $0 to $14999, and $35000 to $44999. We can also take this observation one step further to say that based on the data given, there is a 50% or greater chance of success in the aforementioned range. (As no plays were canceled in this data, I used the assumption that the only pertinent outcomes to consider the probabilities of are the "successful" campaigns and the "failed" ones.) In general, there is very low likelihood of success if the goal amount is set to be $45000 or higher. For Louise, she should note that her greatest chances of success can be achieved by keeping her goal within the range of $0 to $4999, as that yields around 70% chance of success based on historical data. (One caveat is that setting a lower goal will most likely yield higher chances of success as it is easier to raise that amount of money.)


- What are some limitations of this dataset?

The current analysis so far only looks at outcomes based on launch date and goals. There are also many other factors to consider aside from those two. A campaign involves other elements such as methods of outreach, money involved in the campaign etc. It will be useful to consider, for Louise's purposes, the % of outreaches to potential donors that end up being successful, as well as characterizing what makes those particular outreach methods successful. (Although this will involve collecting more data outside of what is given in the raw data.)

But more can be analyzed within the given raw data itself, such as how long a successful campaign takes compared to a failed campaign. 


- What are some other possible tables and/or graphs that we could create?

Another graph to be created can involve finding how long the campaign lasted between the date created and the date ended, and potentially finding a length of time in which chances of success are optimized. For example, the length of time, shown on the x-axis, can be broken down into (a) less than a week, (b) a week to 2 weeks, (c) 2 weeks to 3 weeks, (d) 3 weeks to 4 weeks, (e) a month to 2 months, (f) 2 months or greater etc. This data can yield a line graph set up like the previous two Outcomes graphs, where the "successful" campaigns can be visualized by % of successful, failed, or canceled outcomes.

It will also be useful to plot Outcomes based on Average Donation by each person, with a similar setup as above, where the donation amounts will be broken up to monetary ranges on the x-axis. The reason that data might be useful is because we can visualize whether successful campaigns skew towards smaller or larger donations by each individual. I.e. we can observe whether it is better to have a lot of small-value donations (by a large number of people), or a small number of large-value donations. That can affect how marketing of the campaign is carried out, I.e. focused on reaching a large amount of people or specifically targeting people known to gravitate towards this play subject.
