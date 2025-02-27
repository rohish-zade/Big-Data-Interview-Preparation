## SQL Challenge

### What will be the output of the following sql query?
  ```sql
  with department_counts as(
      select department, count(*) as num_employees
      from employees
      group by department
  )
  select count(*) department_counts:
  ```
- Total number of employees
- Total unique departments
- Sum of all employees across departments
- SQL error

**Ans:** Total unique departments
