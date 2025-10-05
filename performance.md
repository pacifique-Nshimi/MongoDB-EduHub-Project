# MongoDB Query Performance Analysis

This repository demonstrates the impact of indexing on MongoDB query performance. It compares execution times **before** and **after** creating indexes for common queries.

---

## Query Performance Table

| Query                               | Documents Found | Time Before Index (s) | Time After Index (s) |
|-------------------------------------|----------------|----------------------|---------------------|
| Active Students                      | 4              | 0.019374             | 0.000008            |
| Courses containing 'Data Science'    | 1              | 0.005672             | 0.000003            |
| Upcoming Assignments (Next 14 days) | 1              | 0.000918             | 0.000004            |
| Enrollments in Course CRS005         | 1              | 0.000524             | 0.000002            |

## Explanation

### Documents Found
- Shows the number of results returned by each query.
- Queries with 0 results indicate the searched data does not exist in the dataset.

### Time Before Index
- Execution time **without indexes**.  
- MongoDB performs a **full collection scan**, which is slower for large datasets.

### Time After Index
- Execution time **after adding indexes**.  
- Drastic improvement demonstrates the efficiency of indexing.  
- Even queries with 0 results execute faster.

### Observations
- Indexes significantly improve query speed, especially for frequently queried fields (`userId`, `email`, `courseId`, `title`, `category`).  
- Compound indexes improve multi-field queries.  
- Text indexes enable efficient full-text search.  
- Smaller datasets may show minor improvements, but the effect grows with dataset size.

### Recommendations
1. Add indexes on commonly queried fields (`userId`, `email`, `courseId`, `title`, `category`).  
2. Use **compound indexes** for multi-field filtering queries.  
3. Create **text indexes** for full-text searches (`title`).  
4. Use **`explain()`** to verify query plans (look for `IXSCAN` vs `COLLSCAN`).  

---

## Next Steps
- Extend indexing strategy for other collections like `submissions` and `assignments`.  
- Regularly monitor query performance as the dataset grows.  
- Maintain index documentation for team reference.