# **Winter 2022 Data Science Intern Challenge Question 1**
To view my full thought process and my step-by-step approach to analyzing this dataset, please view the jupyter notebook attached to this repo and the comments associated with it. 


Link to dataset the provided and downloaded to be used as a csv file for my program: <br>
https://docs.google.com/spreadsheets/d/16i38oonuX1y1g7C_UAmiK9GkY7cS-64DfiDMNiR41LM/edit#gid=0

<br>
On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis. 
<br><br>

## **Question a) Think about what could be going wrong with our calculation. Think about a better way to evaluate this data.** 

The formula for calculating AOV is as follows: <br>
AOV = Total Order_amount / Total # of orders
<br> <br>
AOV is used as a metric to determine how much that average customer is spending by calculating the total revenue split among all orders. Intuitively, the average customer does not spend $3145.13 per purchase on a "relative affordable item". Although the AOV calculation of $3145.13 is correct, the calculation does not take into consideration of outliers and the price difference between different stores. 
<br><br>
Outliers in a dataset are any point or group of points that are significantly deviated from the rest of the dataset. Given our context of AOV, a data point may be any point where the orders result in an extremely large order amount (or extremely small). 
For example, if there are 100 orders each with an amount of $15 we would have an AOV of $15. However, if we add in a single order of $4000, the AOV would be skewed upwards to $55 and thus portray an inaccurate representation of the AOV per customer. By analyzing the dataset, I have discovered a group of orders caused by a single customer that causes the AOV to be skewed towards a large value. 

Secondly, the AOV in our calculation does not take into consideration of a possible price difference between stores. In the dataset provided, we can observe from the Fig 1. below that each store has a different unit price for its single shoe model. Since each store has a different unit price, the AOV from store to store may be different depending on price or traffic. 

<br>
Fig 1. Unit price comparison
![alt text](https://github.com/oFwano/Shopify-Technical-Challenge-Data-Science-Intern-Winter-2022/blob/master/Question-1/Images/unit-price.png "Unit price comparison")
<br><br>

## **Think about a better way to evaluate this data.**
With varying prices and varying traffic to each store, it become hard to make any meaningful conclusions using AOV alone. In order to evaluate the dataset better, we can measure each store individually to determine if a unit's price has an effect on units purchased or by remeasuring the AOV with the outliers taken out. 
<br><br>
2 Methods to evaluate the data better:
  1. Remove the outliers
  2. Alter the AOV formula:<br>
    Naive:<br>
      *AOV = total revenue / number of orders*<br>
    Altered:<br>
      *AOV = total revenue / number of items sold*



## **Question b) What metric would you report for this dataset?**
The metric I would report for this dataset is the Mode. The Mode, the most frequently occuring order value, is more robust to outliers resulting in less skewed values. In comparison, The Median which is the middle value of all orders maybe skewed towards one extreme if the extremely is significantly deviated from the norm.

## **Question c) What is its value?**

Mode of data['order amount'] = 153
<br><br>

