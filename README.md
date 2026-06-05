# SQL-50_Leetcode


Solutions for SQL 50 Study Plan on LeetCode
[SQL 50 Study Plan](https://leetcode.com/studyplan/top-sql-50/)

## Select Problems

[1757 - Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT product_id 
FROM Products
WHERE low_fats = "Y" AND recyclable = "Y";
```

[584. Find Customer Referee](https://leetcode.com/problems/find-customer-referee/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT name
FROM Customer 
WHERE referee_id is NULL or referee_id !=2;
```
 
[595. Big Countries](https://leetcode.com/problems/big-countries/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT name, population, area 
FROM World
WHERE population >= 25000000 OR area >= 3000000;
```

[1148. Article Views I](https://leetcode.com/problems/article-views-i/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT DISTINCT(author_id) AS id
FROM Views
WHERE author_id = viewer_id
ORDER BY id;
```

[1683. Invalid Tweets](https://leetcode.com/problems/invalid-tweets/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT tweet_id
FROM Tweets
WHERE LENGTH(content) > 15;
```


## Basic Joins Problems

[1378. Replace Employee ID With The Unique Identifier](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
select eu.unique_id, e. name
from Employees e
left join EmployeeUNI eu
on e.id = eu.id;

```

[1068. Product Sales Analysis I](https://leetcode.com/problems/product-sales-analysis-i/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
select p.product_name, s.year, s.price
from Sales s
inner join Product p
ON s.product_id = p.product_id ;
```

[1581. Customer Who Visited but Did Not Make Any Transactions](https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
select v.customer_id ,  COUNT(*) AS count_no_trans
from Visits v
LEFT JOIN Transactions t
on v.visit_id = t.visit_id
WHERE t.transaction_id IS NULL
group by  v.customer_id;

```

[197. Rising Temperature](https://leetcode.com/problems/rising-temperature/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
SELECT  today.id from Weather yesterday
CROSS JOIN Weather today
WHERE DATEDIFF(today.recordDate, yesterday.recordDate) = 1
AND today.temperature > yesterday.temperature;
```

[1661. Average Time of Process per Machine](https://leetcode.com/problems/average-time-of-process-per-machine/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
SELECT machine_id, ROUND(AVG(end - start), 3) AS processing_time
FROM 
(SELECT machine_id, process_id, 
    MAX(CASE WHEN activity_type = 'start' THEN timestamp END) AS start,
    MAX(CASE WHEN activity_type = 'end' THEN timestamp END) AS end
 FROM Activity 
  GROUP BY machine_id, process_id) AS subq
GROUP BY machine_id
```















 
## Like Operator
<img width="735" height="318" alt="image" src="https://github.com/user-attachments/assets/f2ee3d4a-1996-4ab5-adbd-e83efdf81705" />
<br>
## Regular Expresion Pattern
<img width="723" height="273" alt="image" src="https://github.com/user-attachments/assets/3d229441-e655-491d-a878-c5e6438325c7" />
<br>
## Aggregate Function
<img width="834" height="411" alt="image" src="https://github.com/user-attachments/assets/a8a2b710-df60-46a3-b1e8-394c215c9ed1" />





