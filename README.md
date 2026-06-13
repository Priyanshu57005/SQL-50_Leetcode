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

[577. Employee Bonus](https://leetcode.com/problems/employee-bonus/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
SELECT name, bonus
FROM Employee e
LEFT JOIN Bonus b
ON e.empId = b.empId
WHERE bonus < 1000
OR bonus IS NULL
```

[1280. Students and Examinations](https://leetcode.com/problems/students-and-examinations/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
SELECT a.student_id, a.student_name, b.subject_name, COUNT(c.subject_name) AS attended_exams
FROM Students a JOIN Subjects b LEFT JOIN Examinations c
ON a.student_id = c.student_id
AND b.subject_name = c.subject_name
GROUP BY 1, 3
ORDER BY 1, 3 
```

[570. Managers with at Least 5 Direct Reports](https://leetcode.com/problems/managers-with-at-least-5-direct-reports/description/?envType=study-plan-v2&envId=top-sql-50)
```sql
SELECT e.name
FROM Employee AS e 
INNER JOIN Employee AS m ON e.id=m.managerId 
GROUP BY m.managerId 
HAVING COUNT(m.managerId) >= 5
```














 
# SQL Cheat Sheet

## 🔹 LIKE Operator

<p align="center">
  <img width="735" alt="LIKE Operator" src="https://github.com/user-attachments/assets/f2ee3d4a-1996-4ab5-adbd-e83efdf81705" />
</p>

---

## 🔹 Regular Expression (REGEXP)

<p align="center">
  <img width="723" alt="Regular Expression Pattern" src="https://github.com/user-attachments/assets/3d229441-e655-491d-a878-c5e6438325c7" />
</p>

---

## 🔹 Aggregate Functions

<p align="center">
  <img width="834" alt="Aggregate Functions" src="https://github.com/user-attachments/assets/a8a2b710-df60-46a3-b1e8-394c215c9ed1" />
</p>

---

##  Topics Covered

- LIKE Operator (`%`, `_`)
- Regular Expressions (`REGEXP`)
- Aggregate Functions
  - `COUNT()`
  - `SUM()`
  - `AVG()`
  - `MIN()`
  - `MAX()`

---

##  Quick Revision

| Category | Usage |
|----------|--------|
| LIKE | Pattern Matching |
| REGEXP | Advanced Pattern Matching |
| COUNT() | Count Rows |
| SUM() | Sum Values |
| AVG() | Average Values |
| MIN() | Minimum Value |
| MAX() | Maximum Value |




