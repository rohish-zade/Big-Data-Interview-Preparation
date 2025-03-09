## SQL Challenge: SQL Transactions

### Which SQL command is used to manually rollback changes in a transaction?

- A) COMMIT
- B) ROLLBACK
- C) SAVEPOINT
- D) DELETE

**Ans:**  B) ROLLBACK

**Explanation:**
- The ROLLBACK command is used to undo changes made in the current transaction and revert the database to its previous state before the transaction began.

***Lets look at the other options:***

- A) COMMIT: This command permanently saves all changes made within a transaction. It's the opposite of ROLLBACK.
- C) SAVEPOINT: This command creates a marker within a transaction. You can use it with ROLLBACK to undo changes only up to a specific savepoint, rather than the entire transaction.
- D) DELETE: This command removes data from a table, but it's not directly related to transaction control.