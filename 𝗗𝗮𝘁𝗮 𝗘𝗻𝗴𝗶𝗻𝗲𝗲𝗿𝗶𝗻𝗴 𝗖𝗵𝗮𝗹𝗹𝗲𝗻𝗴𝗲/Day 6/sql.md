## SQL Challenge: Subquiries

### Which of the following queries correctly uses a subquery?
- A) SELECT * FROM employees WHERE salary > (SELECT AVG(salary) FROM employees)
- B) SELECT AVG(salary) FROM employees GROUP BY department
- C) SELECT salary FROM employees WHERE department = 'HR'
- D) SELECT * FROM employees

**Ans:** A) SELECT * FROM employees WHERE salary > (SELECT AVG(salary) FROM employees)

**Explanation:**
- ubquery: A subquery is a query nested within another query. In this case, the subquery `(SELECT AVG(salary) FROM employees)` calculates the average salary of all employees. The main query then selects employees whose salary is greater than this average.