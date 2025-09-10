# Day 01 — Rising Temperature
**LeetCode:** https://leetcode.com/problems/rising-temperature/

**Problem summary:** Return dates where today's temperature is higher than the previous day.

**SQL Solution:**
```sql
SELECT recordDate
FROM (
  SELECT recordDate, temperature,
         LAG(temperature) OVER (ORDER BY recordDate) AS prev_temp
  FROM Weather
) t
WHERE temperature > prev_temp;
