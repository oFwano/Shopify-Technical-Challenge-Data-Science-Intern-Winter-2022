# Shopify-Technical-Challenge-Data-Science-Intern-Winter-2022 Question 2

Question 2: For this question you’ll need to use SQL. Follow this link to access the data set required for the challenge. Please use queries to answer the following questions. Paste your queries along with your final numerical answers below.

a) How many orders were shipped by Speedy Express in total?
b) What is the last name of the employee with the most orders?
c) What product was ordered the most by customers in Germany?

## **Question A) How many orders were shipped by Speedy Express in total?**
```
SELECT Count(ShipperId) as "Orders shipped by Speedy Express"
FROM Orders
Where ShipperId = 1
```
Answer: 54


## **Question B) What is the last name of the employee with the most orders?**
``` 
Select Employees.LastName
FROM Orders, Employees
Where Orders.EmployeeID = Employees.EmployeeId
Group by Orders.EmployeeID
Having Count(Orders.OrderId)
Order by Count(Orders.OrderId) Desc
Limit 1
``` 
Answer: Peacock

## **Question C) What product was ordered the most by customers in Germany?**

