## Data Modeling Challenge

### Which approach correctly models a many-to-many relationship between students and courses?
- Adding a course_id column in the students table
- Adding a student_id column in the courses table
- Creating a student_courses junction table
- Using only foreign keys without a separate table

**Ans:** Create a student_courses junction table

**Explanation:**
- Many-to-many relationships require an intermediate (junction) table to avoid redundancy and maintain normalized data.
- `Junction Table:` A junction table (also known as an associative table or bridge table) is used to resolve many-to-many relationships. It contains foreign keys referencing the primary keys of the two related tables (students and courses).
- The correct schema:
  ```sql
  CREATE TABLE student_courses (
      student_id INT REFERENCES students(student_id),
      course_id INT REFERENCES courses(course_id),
      PRIMARY KEY (student_id, course_id)
  );
  ```
- This approach ensures scalability and allows a single student to enroll in multiple courses while multiple students enroll in the same course.
