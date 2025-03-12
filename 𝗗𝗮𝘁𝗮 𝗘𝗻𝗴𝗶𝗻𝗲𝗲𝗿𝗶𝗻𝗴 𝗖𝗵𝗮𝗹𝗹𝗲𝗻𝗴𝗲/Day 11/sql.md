## SQL Challenge: SQL Isolation Levels

### Which SQL isolation level ensures that no other transaction can read uncommitted changes?

- A) READ UNCOMMITTED
- B) READ COMMITTED
- C) REPEATABLE READ
- D) SERIALIZABLE

**Ans:** (B) READ COMMITTED.

**Explanation:**
- READ UNCOMMITTED: Allows transactions to read uncommitted changes (Dirty Reads).
- READ COMMITTED: Ensures that a transaction can only read committed data, preventing dirty reads.
- REPEATABLE READ: Prevents dirty and non-repeatable reads but allows phantom reads.
- SERIALIZABLE: The strictest level, preventing dirty reads, non-repeatable reads, and phantom reads.