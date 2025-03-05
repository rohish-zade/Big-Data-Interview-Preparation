## SQL Challenge: self joins

### Which SQL operation is best for finding employees who have the same manager?
- A) INNER JOIN
- B) SELF JOIN
- C) FULL OUTER JOIN
- D) UNION

**Ans:** B) SELF JOIN

**Explanation:**
- A SELF JOIN is a join where a table is joined with itself. In this case, you can use a self-join on the employee table to find employees who share the same manager by comparing the manager_id column.