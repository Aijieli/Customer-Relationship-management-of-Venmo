# Venmo Social Network and RFM Analysis

For customer management, Venmo wants to figure out what would increase the customers' transactions through the app. 

There are many factors would affect the number of transactions. We mainly focused on three factors here, the spending behavior prfoile metrics, network metrics and RF metrics respectively.

## Spending behavior profile metrics
- the proportion of corresponding transaction type
We defined the transaction types by the description of the transaction including both words and emojis. For each users there would be more than one type for a transaction. After defining the transaction types, we calculated the proportion of the types in total transactions and used these in regression.

## Network Metrics

## RF metrics (Recency, Frequency)
- Recency
Recency was calculated as the days since last transaction time for the users. For example, if we used 5/18 as the end time, the user last purchased on 5/15, and then the recency would be 3 days.

- Frequency
