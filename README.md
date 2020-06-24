# Venmo Social Network and RFM Analysis

For customer management, Venmo wants to figure out what would increase the customers' transactions through the app. 

There are many factors would affect the number of transactions. We mainly focused on three factors here, the spending behavior prfoile metrics, network metrics and RF metrics respectively.

## Spending behavior profile metrics
- the proportion of corresponding transaction type<br>
We defined the transaction types by the description of the transaction including both words and emojis. For each users there would be more than one type for a transaction. After defining the transaction types, we calculated the proportion of the types in total transactions and used these in regression.

We used classification dictionary to define the corresponding transaciton types and there were 10 types, which were activity, cash, event, food, illegal, others, people, transportation, travel and utility.

## Network Metrics
- Friends and Friends of Friends<br>
Firends refers to the number of friends the user has for a certain period. Friends of friends refers to the number of the users' friends' friends for a certain period.

- Clustering Coefficient<br>
<img src="https://github.com/Aijieli/Venmo-Social-Network-and-RFM-Analysis/blob/master/clustering%20coefficient.png" width="600" height="80">

- Page Rank<br>
PageRank computes a ranking of the nodes in the graph G based on the structure of the incoming links. It was originally designed as an algorithm to rank web pages. Here we used each user as nodes and each transaction as en edge.

## RF metrics (Recency, Frequency)
- Recency<br>
Recency was calculated as the days since last transaction time for each users. For example, if we used 5/18 as the end time, the user last purchased on 5/15, and then the recency would be 3 days.

- Frequency<br>
Frequency was calculated as the number of transactions for a certain period for each user. 

## Regression
For regression part, our target variable was the number of transactions for the users in his first 12 months and we firstly regressed only on Rencency and Frequency metrics. Then we added spending behavior profile metrics. Thirdly, we regressed only on social network metrics. Lastly, we regreesed on social network metrics and spending behavior profile metrics.

From the coefficients, we can see that the coefficient of the Pagerank has the biggest effect size, which indicates that Pagerank is the most informative predictors.

Furthermore, as we introduced the time interval in the users' lifetime. It could be further used as the base of A/B test as a method to deal with long term effect with short-term variables, a common dilemma of A/B test.
