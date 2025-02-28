## ETL Challenge: Airflow DAG Dependencies

###  What is the best way to ensure a downstream task runs only after all upstream tasks are complete?
- Set task dependencies explicitly
- Use sleep() function
- Manually trigger the next task
- Airflow does not support dependencies

**Ans:** Set task dependencies explicitly.

**Explanation:**
- `Explicit Task Dependencies:` This is the standard and reliable way to manage task execution order in workflow management systems like Airflow. By defining dependencies, you tell the system that a task should only start once its specified upstream tasks have successfully completed.

- **Why the other options are incorrect:**
  - `Use sleep() function:` Using sleep() introduces arbitrary delays and does not guarantee that upstream tasks have finished. It's unreliable and not scalable.
  - `Manually trigger the next task:` This is not automated and defeats the purpose of workflow automation. It's also prone to human error.
  - `Airflow does not support dependencies:` This is false. Airflow is designed to manage task dependencies.