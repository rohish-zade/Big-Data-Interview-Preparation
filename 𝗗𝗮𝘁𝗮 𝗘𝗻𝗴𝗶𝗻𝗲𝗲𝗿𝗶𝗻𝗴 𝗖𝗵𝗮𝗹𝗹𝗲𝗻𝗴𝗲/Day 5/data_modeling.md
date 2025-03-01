## Data Modeling Challenge: Indexing strategies

### Which index type is most effective for filtering large datasets based on a range condition?
- A) Hash index
- B) B-Tree index
- C) Full-text index
- D) None of the above

**Ans:** B) B-Tree index

**Explanation:**
- `B-Tree index:` This is a tree-like data structure that is well-suited for range queries. It allows the database to efficiently locate rows that fall within a specified range of values. This is because B-trees store data in a sorted order, making it easy to traverse the tree and find matching rows.

- ***Here's why the other options are not the best fit for range conditions:***
  - `Hash index:` Hash indexes are good for equality comparisons but not ideal for range queries. They use a hash function to map values to locations in the index, which doesn't preserve the order of values.
  - `Full-text index:` Full-text indexes are designed for searching text data and are not optimized for range conditions on numerical or date values.
  - `None of the above:` As explained, B-tree indexes are specifically designed to handle range conditions efficiently.