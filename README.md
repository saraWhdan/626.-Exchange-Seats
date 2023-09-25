# 626. Exchange Seats
### Problem Link & Description : [Exchange Seats](https://leetcode.com/problems/exchange-seats/?envType=study-plan-v2&envId=top-sql-50)
## Solution
```sql
SELECT 
    id,
    CASE
        WHEN id % 2 = 0 THEN LAG(student) OVER (ORDER BY id)
        ELSE ISNULL(LEAD(student) OVER (ORDER BY id), student)
    END AS student
FROM seat
