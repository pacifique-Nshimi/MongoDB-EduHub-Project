# MongoDB-EduHub-Project

## Table of Contents

- [Project Overview](#project-overview)  
- [Prerequisites](#prerequisites)  
- [Installation & Setup](#installation--setup)   
- [Key Features](#key-features)  
- [Project Structure](#project-structure)  
- [Challenges](#challenges)  
- [Solutions](#solutions)  

## Project Overview  

EduHub is a MongoDB-based database system for an online learning platform.  
This project demonstrates my understanding of NoSQL database design, document modeling, and MongoDB operations using Python and PyMongo.  

### What This Project Does:
- Manages users (students and instructors)  
- Handles course creation and enrollment  
- Tracks student progress and assignments  
- Provides analytics through aggregation queries  

## Key Features

- 6 MongoDB collections with proper relationships  
- Complete CRUD operations  
- Complex aggregation pipelines for analytics  
- Performance optimization with indexes  
- 20+ users, 8 courses, and realistic sample data

## Prerequisites  

Before running this project, ensure you have:  

- MongoDB v8.0 or higher [Download](https://www.mongodb.com/try/download/community)  
- Python 3.8 or higher [Download](https://www.python.org/downloads/)  
- Jupyter Notebook (for running the interactive notebook) [Install Guide](https://jupyter.org/install)

## Installation & Setup  

### Step 1: Connect to MongoDB  

bash
# Make sure MongoDB is running

# On Windows (if installed as service):
net start MongoDB

# On macOS/Linux:
mongod --dbpath /path/to/your/data/directory

# Start Jupyter Notebook
jupyter notebook

# Navigate to notebooks/eduhub_mongodb_project.ipynb
# Run all cells to see the complete implementation


## Project Structure
```

mongodb-eduhub-project/
│
├── README.md                          
├── notebooks/
│   └── eduhub_mongodb_project.ipynb  
|
├── eduhub_queries/
│   ├── crud_operations.ipynb
│   ├── advanced_queries.ipynb
│   └── index_performance.ipynb
|
├── data/
│   ├── users.json                   
│   ├── courses.json                 
│   ├── enrollments.json
│   ├── lessons.json
│   ├── assignments.json
│   └── submissions.json
|
└── docs/
    ├── performance_analysis.md      
    ├── schema_diagram.md           
    └── presentation.pptx     
```

## Challenges

### Challenge 1: Complex Aggregations
Calculating student performance metrics across multiple collections.

### Challenge 2: Query Performance
Slow queries when filtering courses by multiple criteria.

### Challenge 3: Referential Integrity
MongoDB doesn’t enforce foreign key constraints like SQL databases.

---

## Solutions

### Solution 1: Complex Aggregations
Used MongoDB’s $lookup operator to join collections and $addFields to compute calculated values within aggregation pipelines.

### Solution 2: Query Performance
Created compound indexes on frequently queried fields (category + level) which reduced query time by 94%.

### Solution 3: Referential Integrity
Implemented application-level validation checks before insertions and deletions to maintain data consistency.
