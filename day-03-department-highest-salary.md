# Day 03 — Department Highest Salary
**LeetCode:** https://leetcode.com/problems/department-highest-salary/

**Problem summary:** For each department, show the highest salary and department name.

**SQL Solution:**
```sql
SELECT d.Name AS Department, e.Name AS Employee, e.Salary
FROM Employee e
JOIN Department d ON e.DepartmentId = d.Id
WHERE e.Salary = (
  SELECT MAX(Salary)
  FROM Employee
  WHERE DepartmentId = d.Id
);
