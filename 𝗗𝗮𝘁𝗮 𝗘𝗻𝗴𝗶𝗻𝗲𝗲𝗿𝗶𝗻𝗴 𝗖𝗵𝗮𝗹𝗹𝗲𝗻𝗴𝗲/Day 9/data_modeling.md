## Data Modeling Challenge: Denormalizaton Trade-offs

### What is a key downside of denormalization?

- A) Slower queries
- B) Increased redundancy
- C) Reduced data integrity
- D) Both B and C

**Ans:** D) Both B and C

**Explanation:**

Denormalization involves adding redundancy to improve query performance, but it comes with downsides:
- A) Slower queries ❌ → Denormalization usually speeds up queries because data is pre-joined, reducing the need for complex joins. However, it can slow down updates and inserts due to redundancy.
- B) Increased redundancy ✅ → Denormalization duplicates data across tables, which can lead to increased storage usage and potential inconsistencies.
- C) Reduced data integrity ✅ → Since the same data appears in multiple places, there is a higher risk of inconsistencies if updates are not properly managed.