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

```
SELECT tweet_id
FROM Tweets
WHERE LENGTH(content) > 15;
```


## Basic Joins Problems
















<img width="735" height="318" alt="image" src="https://github.com/user-attachments/assets/f2ee3d4a-1996-4ab5-adbd-e83efdf81705" />



