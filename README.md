# SQL-50_Leetcode
SQL 50 - LeetCode

Solutions for SQL 50 Study Plan on LeetCode
#[SQL 50 Study Plan](https://leetcode.com/studyplan/top-sql-50/)

#[1757 - Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT product_id 
FROM Products
WHERE low_fats = "Y" AND recyclable = "Y";
```

#[584. Find Customer Referee](https://leetcode.com/problems/find-customer-referee/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT name
FROM Customer 
WHERE referee_id is NULL or referee_id !=2;
```
 
