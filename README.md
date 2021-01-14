# README

###  Problem Statement: What is the correlation between state spending per pupil and resulting SAT/ACT scores? Will higher spending correlate with higher scores on a state level?


### Outside Research:
Outside Research obtained from downloading excel sheet for education funding by state from: https://www.governing.com/finance/Education-Spending-Per-Student-By-State.html

During research it was important to keep in mind that states have different populations so there funding will show accordingly (lower populations will require less funding, high pops will require higher funding). That is why I wanted to make sure I found a data set that would include the funding per pupil, which gives us a more comparable, equally scaled variable to work with.

Per website above: Nationally, the 2018 data indicates $12,612 is spent on public education per student, up nearly $1,000 as compared to the 2016 data. Significant variation exists across states; New York spends more than $24,000 per student, while states like Utah and Idaho report spending less than a third as much. 

I wanted to include the above excerpt because with just this tidbit it leads me to believe that the observed increase in investing in students is motivated by the belief that there is a positive correlation between spending per pupil and "success" (higher scores). Let's unpack some of the data and see if we can draw any correlations.



### Data Dictionary:
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|2018 ACT/ACT/Public School Spending Per Student By State|Indicates the specific state of the country|
|sat_participation|float|2018 SAT| The reported participation rate of pupil's that took the SAT across the state|
|ebrw|int|2018 SAT|The statewide average score for the Evidence-Based Reading and Writing section of the SAT|
|math|int|2018 SAT|The statewide average score for the Math section of the SAT|
|sat_total|int|2018 SAT|The combined (total) statewide average score for the entire SAT|
|act_participation|float|2018 ACT| The reported participation rate of pupil's that took the ACT across the state| 
|act_total|int|2018 ACT|The reported statewide average score for the ACT exam|
|total_spending_per_pupil|float|2018 Public School Spending Per Student By State|How much total money is spent on public education per student| 
|total_spending|int|2018 Public School Spending Per Student By State|Total amount of public education spending per state|
|instruction_spending_per_pupil|float|2018 Public School Spending Per Student By State|How much money is spent on salaries for teachers and teacher aides, textbooks, supplies and purchased services per student| 
|total_instruction_spending|int|2018 Public School Spending Per Student By State|How much money is spent on salaries for teachers and teacher aides, textbooks, supplies and purchased services in total per state|
|support_spending_per_pupil|float|2018 Public School Spending Per Student By State|How much money is spent on adminstrative expenses and support staff per student| 
|total_support_spending|int|2018 Public School Spending Per Student By State|How much money is spent on adminstrative expenses and support staff in total per state| 



### Cleaning: 
The most important part of cleaning was to ensure proper data integrity. This meant checking for null values or any obvious incorrect observances and remedying them. Fortunately the data was well recorded and no issues arose. Next was to find ways to connect our data and merge them into one workable set. This was relatively easy since there was a common column "state" amongst all three which allowed me to join the sets using that column. From there all that was left was minor tweaks and removing anything that might create a problem for my analysis stage (converting percentages to floats, lower case columns, removing any spaces etc...) 



### Key Analysis:
Once data was properly clearned and merged, my main focus was to be able to utilize the scatter plot effectively. While I've included just a nationwide look at just spending per pupil and the respective ACT and SAT scores, I wanted to ensure everything was kept in proper context. What I mean by this is that we are ensuring we are comparing our funding to the proper scores. If a state doesn't take the SAT at a high rate, it doesn't make much sense to heavily consider the effect that funding has on their SAT score. That is why I founf it important to group states into two groups: sat "preferred" and act "preferred" ("preferred" is used to indicate the state records a higher participation rate for this exam over the other). Although in order to give us a more complete picture, I wanted to make sure to include my analysis for both SAT and ACT on a national level to see if we could uncover any patterns through with those cuts. 



### Conclusions/Recommendations: 
Based on the analysis, if states want their students to succeed on either the SAT and more demonstrably the ACTs I would suggest allocating more spending on funding per pupil. While this seems like an intuitive suggestion, I think it's important to also note that there is no clear direct cause-effect relationship. Higher spending doesn't always result in higher scores as there are (as we might expect) many factors in play. But I would argue that shown from specifically our scatter plot comparisons, there is enough of a trend towards the belief that the more you allocate towards student spending, the better the testing results. We must also keep these findings contextualized which is why it was important to understand the participation rates of each exam across the state. In order to maximize our analysis we want to make sure we compare funding to the more frequent occuring exam scores. Otherwise if we are a state with lower funding but see high SAT scores (at only a 4% participation rate) and then underperforming ACT scores at a much higher rate, we won't be mislead to assume our funding is sufficiently allocated. 

#### Sources:
state_funding_2018.csv: downloaded as an xlsx file from: https://www.governing.com/finance/Education-Spending-Per-Student-By-State.html (then converted to csv with jupyter notebook)
act_2018.csv: class repo
sat_2018.csv: class repo