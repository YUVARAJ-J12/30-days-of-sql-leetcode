
# Day 02 — Employees Earning More Than Their Managers
**LeetCode:** https://leetcode.com/problems/employees-earning-more-than-their-managers/

**Problem summary:** Return employees who earn more than their direct manager.

**SQL Solution:**
```sql
SELECT e.Name AS Employee
FROM Employee e
JOIN Employee m ON e.ManagerId = m.Id
WHERE e.Salary > m.Salary;
