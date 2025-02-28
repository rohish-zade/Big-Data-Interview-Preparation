## SQL Challenge

### What will be the output of the following sql query?
  ```sql
  select name, salary,
  row_number() over(partition by department order by salary desc) as rank
  from employees;
  ```
- Assigns a rank to each employee within a department
- Counts total employees
- Generates unique numbers across all employees
- SQL Error

**Ans:** Assigns a rank to each employee within a department

**Explanation:**
- ROW_NUMBER() is a window function that assigns a unique rank to each row within a partition.
- PARTITION BY department_id ensures ranking restarts for each department.
- ORDER BY salary DESC ranks employees within their department based on salary (highest first).