

# Modeling Presidential Election Voting 

#### Kendall Lipsey, Thomas Coleman, Tanner Miles, and Mukila Rajasekar; University of North Carolina, Wilmington  

## ABSTRACT  

As America’s political polarization increases, elections are becoming more important in American’s everyday lives. In 2016, the US experienced an 18% increase in news-consumption from the year prior (“Nielsen Report”, 2017). Daily, the world watched political candidates campaigning for the presidency of the United States. For a candidate to maximize the impact and efficiency of campaigning, he/she must choose locations that have a chance for changing votes in their direction. For example, Donald Trump campaigning in California would be an inefficient use of resources due to little chance to swing the state’s electoral vote for the Republican party, but Donald Trump campaigning in North Carolina (as he did, often) has more potential for benefit. North Carolina is a state that tends to swing, allowing the politician to potentially win more electoral votes. A model was created to predict the total change in votes cast for one party over the other using county-level demographics. Based on the findings, which counties/areas would be most beneficial for candidates to campaign to secure the most votes will be predicted. This paper focuses on the only the two major political parties, Republican and Democrat, and targets the 2016 election due to its engaging nature. Differences on several variables between 2012 and 2016 were used to determine changes in votes cast for president.  

## INTRODUCTION  

Politics are becoming an increasingly important part of Americans’ lives. A Gallup poll found that under the 2016 election, Americans following the election “very closely” spiked from 31 to 39 percent compared to the previous election, with Republicans having the highest closely following percentage (Auter, 2016). How were Republicans able to do this in the 2016 election? Age, voter issues, and state of the economy all had roles to play in turning up the heat on the 2016 election, but and main ingredient was at play here: the strategic selection of campaigning locations.  

 

President Donald Trump dominated the news stage and rally arena, Donald Trump was often known for his large rally size and had almost triple the free news coverage of Hillary Clinton (Confessere and Yourish, 2016). Arguably a large contribution to his success, he hosted more rallies/campaigns in 13/15 battleground states compared to Hillary Clinton (Smith and Kreutz, 2016). There are two problems to focus on with choosing battleground counties: 1) What factors, and in what areas, should political strategists consider when evaluating how to receive the greatest number of votes per state? 2) Depending on the strategy, where should time, effort, and money be allocated to win the greatest number of votes per state? 

 

Focus was put on solving these issues through two methods: 1) Created a model to predict which counties are subject to the greatest change in total votes from one election to the next. 2) Using the findings from method 1, the most efficient campaigning areas were. The goal of a campaign/rally is to attract the most people, keeping this in mind, this was based on population and population density. 

 

When political scientists and strategists plan a path to victory for a presidential candidate, the complexity of the electoral college weighs heavily. Whether to focus on landslide victories in far leaning states or leveling out competitive ‘purple’ states relies on how many votes you can win on a state-level. However, state lines do not adequately illustrate the differences and diversity represented within each state. Therefore, zooming in and investigating nuances found on a county level can help identify patterns.  

## METHODS 

Although there are many comprehensive resources available, there was no single data source which had all the desired variables for every county in the USA. Data was collected for the years 2012 and 2016 by FIPS code, a unique code issued to each county. 

 

Information was gathered on unemployment and economic composition by labor type (which was condensed to blue- and white-collar labor).  Investigated races include White, African American, Hispanic, American Indian, and Asian American. Highest educational attainment was collected on high school, associate degree, bachelor's degree, and graduate degree. This was later condensed to bachelor's degree or higher (combining bachelor and graduate degrees) and associate degree or lower (combining associate and high school).  Population density and voter turnout data was collected. Religious affiliation information was gathered including Orthodox Jewish, Black Protestant, Mainline Protestant, Catholic, Evangelical, total religious, and other religious affiliations. Median household income change (from 2008 to 2012 and 2012 to 2016) was collected. Lastly, total vote, Republican vote, and Democrat vote counts were included. Only party frontrunners (Republican and Democrat) votes were considered.  

 

All the datasets were transposed by FIPS code and year, then merged into one dataset. This dataset, as well as all sources, are available in the  SAS Election Project Information GitHub folder. Many observations were excluded for Alaska as it is the only state which does not use FIPS codes, but rather boroughs and judicial districts. Also, some vote information was missing for a few counties in Arizona in 2016.   

 

The Factor Procedure was used for dimension reduction from 17 variables to 8 factors. Both the static number represented by each variable (for example, the percentage of the population which is Hispanic) and the change over time (for example, the change in the percentage of the population which is Hispanic) were evaluated. To standardize the variables not used in factors, the Standard Procedure was employed. A response variable was selected to incorporate change over time and party selection. The difference in the number of votes was calculated by subtracting the number of Democrat votes cast (per county, per year) from the number of Republican votes cast. The difference was then calculated between 2016 and 2012. Therefore, a negative forty (-40) represents that in 2016 forty more votes went Democratic in 2012. Finally, the GLMSelect Procedure was used to choose from all applicable variables, factors, and their interactions,  and the final predictive model was produced using the GLM Procedure. Visualizations were further produced in SAS Studio (Figures 1-28) and stored on Github (link following Conclusion).  

 

To find the predicted values and the corresponding residuals (error), the GLM procedure was employed. This residual was used to determine the accuracy of the predicted values and for visualizations.  

 

 

 

 

## RESULTS 

The model, shown in table 1, resulted in an R-Squared of 0.334595, implying 33% of the variance of the response variable can be accurately explained by the model. The model resulted in a p-value less than .0001, suggesting it is highly statistically significant.  

Moreover, when the model was applied to all counties, 419 counties were found to be accurately predicted (within one confidence interval 0). 

## DISCUSSION 

Due to the numerous variables, interactions, and the multifaceted application of several of the variables, interpreting the model is complex.  

### POPULATION DENSITY  

Text BoxOne variable worth further investigation is population density. Intuitively, the greater the population density, the more impact other factors have. However, a more nuanced approach shows that, when ordering the variables in terms of the greatest change in votes, interactions with population density rank as the top four. Figure 1 illustrates as the population density increases, the average Republican margin decreases substantially. However, Figure 2 illustrates the sum (rather than the average) number of Republican votes over Democrat votes is far greater in less dense areas. Figure 3 highlights the inverse of this relationship. Although there are more votes gathered for Democrats in areas with high population density, areas with low population density far outnumber the dense areas with the sum of the votes leaning Republican. Of course, as population density interacts with other variables in the model, it cannot be considered in isolation. With that being said, the urban-rural divide still proves to have a heavy weight in the model predictions.  

### LABOR TYPE 

The top two interactions are between population density and the change in labor composition (blue-collar and white-collar). For example, the highest ranked term showing a change of 11,079 votes from the interaction of blue-collar and population density can be interpreted as a hyper-actualization of the urban-rural divide paired with labor composition. This shows that if the change of blue-collar workers in a county is one standard deviation below the mean and population density is two standard deviations above the mean (a city), the model predicts a decrease of 22,000 votes for the Republican margin. 

 

Figure 4 shows as the percentage of white-collar laborers increases, the average number of Republican votes over Democrat votes decreases. This relationship can further be seen in the model’s second ranked term, in order of greatest change in votes, for the white collar labor, population density interaction. In this instance, a county with a population density one standard deviation above the mean and a change in white collar laborers one standard deviation above the mean, the model would predict an increase in the margin favoring the Republican candidate of 6608 votes. 

 

Figure 5 shows as the change in the percentage of blue-collar laborers increases, the average number of Republican votes over Democrat votes decreases. However, further investigation (illustrated in Figure 6 & 7) highlights the interaction of population density on labor composition. Figures 6 & 7 show the sum of blue-collar increases leading to a large increase in Republican votes, yet a large increase in blue-collar composition is correlated with negligible increase in votes. It is hypothesized that this is indicative of population density as counties with high blue-collar compositions are often of low population density. 

 

### RACE 

Race also affects the model prediction. Figure 8 shows how racial composition affects the average number of Republican votes over Democrat votes.  Figures 9 and 10 show as the percentage of Hispanic population increases, the average number of republican votes over Democrat votes decreases. However, the model’s sixth ranked term (in order of greatest change in votes) is –3,830 percent Hispanic, population density interaction; showing that population density and racial composition have a strong weight together. For example, the model predicts an increase of 7,660 Republican votes over Democrat votes in a county with a Hispanic population two standard deviations less than the mean and population density one standard deviation below the mean. This relationship can be seen in Figures 11 & 12. A similar relationship is seen with the African American percentage of a population, represented by the race factor in the model (positive values in this factor indicate a higher percentage of African American population) and can be seen in Figures 13, 14, and 15.  

 

In addition to the racial composition, the change in racial percentages between 2012 and 2016 affect the model predictions. This is best illustrated by the change in White percentage (as it has the largest percentage in most counties). Figure 16 shows that as the change in the percentage of a white population decreases, the average number of Republican votes over Democrat votes also decreases. The model incorporates this in the form of the change in race factor, where a negative factor represents a higher percentage of white (vs. black) in a population. The model would predict a county with a white population one standard deviation above the mean and a population density one standard deviation below the mean would have 1,930 more Republican votes over Democrat votes. 

 

### RELIGION 

Religion carries some weight on the model as well.  Figure 17 shows a moderate evangelical population (40-45%) is correlated with the highest average number of Republican votes over Democrat votes. A couple outliers can be noted in counties with 51-100 (per 1000) evangelical participants as these counties include Santa Barbara and San Francisco which lean heavily Democrat. Additionally, counties with 250-300 (per 1000) evangelical participants include Houston and Dallas, Texas. The model incorporates the evangelical population in many terms, most notably as an interaction with population density. The model would predict that a county with a population density one standard deviation below the mean and an evangelical population one standard deviation above the mean to receive 4,934 more Republican votes over Democrat votes. 

 

Figure 18 shows that a moderate catholic population (50-60%) is correlated with the highest average number of Republican votes over Democrat votes. Outlier counties encompassing Los Angeles (with catholic population of 450-500 per 1000) and in New York and Maine (with catholic populations of 350-400) lean those brackets Democrat. The model predicts that a county with catholic population one standard deviation above the mean would result in 2,225 more republican votes over Democrat votes. Additionally, the model incorporates Catholicism as an interaction with population density.  

 

The religious population of all denominations and number of Republican over Democrat votes can be found in Figure 19. The interaction between population density and both catholic and evangelical rates can be illustrated when comparing Figures 20 and 21 (in Figure 22). Although there are more votes gathered for Democrat candidates in areas with low religion, areas with low population density and high religion far outnumber the dense areas and the sum of the votes lean Republican.  

 

### GEOGRAPHY 

Figure 23 displays the best 10% of predictions geographically on a county level. The model is most accurate in predicting counties in the south and spread out through the mid-west.  The model can predict 360 counties within 500 votes cast. Since population density has shown such strong weight in the model, the more rural areas in the south and the mid-west to be more accurately predicted.   

 

Inversely, when looking at Figure 24, the areas where the model struggled to accurately predict the change in votes to be much denser, higher populated areas. Places such as Los Angeles, New York City, and Miami, all had poor predictions.  This is also due to the strong weight of the population density variable.  Since the population density of these areas are far greater than rural areas, this causes the model to severely skew the predictions.  This poses an error with the model that will continue to be identified and improve on.    

 

Figure 25 shows the difference in total votes between the years 2012 and 2016. As mentioned earlier in the 'Methods' section, positive values or the red zones are associated with Republican votes received and negative or blue zones represent votes received by Democrats. That is, the larger positive values indicate that a large number of votes went to the Republican party in 2016 than in 2012. Similarly, the larger negative values are associated with a large number of votes for the Democratic Party. These big vote difference regions are clearly seen in Figure 26. For example, in Figure 27 many counties in California have a high concentration of Democratic votes in 2016. The New York state map in Figure 28 shows a high concentration of Democratic votes only in and around the New York City while most of the other counties in this state have higher number of Republican votes.  

## CONCLUSION 

Through the model there have been some take-aways: race, gender, religion, and labor type affect the number of votes for a party for a given county. Add in population density, and everything changes. The findings of this model, and the highest-ranking variables, should be considered when planning a political campaign.  

 

One issue with the model being used in the future is the changing composition of political parties in the US. Americans are becoming more diverse, educated, and agnostic. For example, as America has become more educated, the education composition of each political party has flipped (Johnson, 2016). With the 2020 election approaching, there is an opportunity for additional data to make the model more accurately portray the current political makeup of the US. In addition, updated population and population density will be incorporated, using the 2020 census, to create a model that identifies the most efficient campaigning locations for candidates in battleground areas. 

 


## REFERENCES 

Auter, Z. (2019, May 24). Number of Americans Closely Following Politics Spikes. Retrieved January 5, 2020, from https://news.gallup.com/poll/195749/number-americans-closely-following-politics-spikes.aspx. 

Confessore, N., & Yourish, K. (2016, March 15). $2 Billion Worth of Free Media for Donald Trump. Retrieved January 5, 2020, from https://www.nytimes.com/2016/03/16/upshot/measuring-donald-trumps-mammoth-advantage-in-free-media.html. 

Johnson, B. (2019, December 31). The changing composition of the U.S. political parties. Retrieved January 5, 2020, from https://www.people-press.org/2016/09/13/1-the-changing-composition-of-the-political-parties/. 

The Nielsen Total Audience Report: Q4 2016. (2017, March 4). Retrieved January 5, 2020, from https://www.nielsen.com/us/en/insights/report/2017/the-nielsen-total-audience-report-q4-2016/. 

Smith, C., & Kreutz, L. (2016, November 7). Hillary Clinton's and Donald Trump's Campaigns by the Numbers. Retrieved January 5, 2020, from https://abcnews.go.com/Politics/hillary-clinton-donald-trumps-campaigns-numbers/story?id=43356783. 

 


 
 

SAS and all other SAS Institute Inc. product or service names are registered trademarks or trademarks of SAS Institute Inc. in the USA and other countries. ® indicates USA registration.  

Other brand and product names are trademarks of their respective companies.  

