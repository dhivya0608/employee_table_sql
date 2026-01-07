# employee_table_sql
# SQL Practice Questions – Employee Joining Analysis

This section contains **SQL interview-style questions with answers** based on the
employee table shown below.  
Focus areas include **date functions, experience calculation, and aggregation**.

---

## 📌 Table Structure

**Table Name:** `employees`

| Column Name     | Description |
|-----------------|------------|
| employee_id     | Employee ID |
| employee_name   | Employee name |
| joining_date    | Date of joining |
| age             | Employee age |
| role            | Job role |
| location        | Work location |
| salary          | Employee salary |

---

## 📊 Sample Data
-- CREATE TABLE
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(50),
    joining_date DATE,
    age INT,
    role VARCHAR(50),
    location VARCHAR(50),
    salary DECIMAL(10,2)
);

-- INSERT DATA
INSERT INTO employees VALUES
(1,  'John Smith',        '2020-01-15', 30, 'Software Engineer',    'New York',       80000.00),
(2,  'Jane Doe',          '2019-03-22', 28, 'HR Manager',           'Los Angeles',    75000.00),
(3,  'Alice Johnson',     '2021-06-10', 35, 'Data Analyst',         'Chicago',        70000.00),
(4,  'Bob Brown',         '2022-02-05', 40, 'Project Manager',      'Houston',        90000.00),
(5,  'Charlie White',     '2023-05-30', 26, 'Intern',               'Miami',          30000.00),
(6,  'David Wilson',      '2019-08-12', 32, 'Software Engineer',    'Seattle',        82000.00),
(7,  'Emily Davis',       '2020-11-20', 29, 'HR Assistant',         'San Francisco',  60000.00),
(8,  'Frank Miller',      '2019-07-15', 38, 'Data Scientist',       'Boston',         95000.00),
(9,  'Grace Lee',         '2022-03-18', 31, 'Project Coordinator',  'Denver',         72000.00),
(10, 'Henry Garcia',      '2023-01-25', 27, 'Intern',               'Austin',         35000.00),
(11, 'Isabella Martinez', '2021-04-30', 34, 'Software Engineer',    'New York',       81000.00),
(12, 'Jack Thompson',     '2020-09-10', 36, 'HR Manager',           'Los Angeles',    77000.00),
(13, 'Karen Robinson',    '2021-12-05', 29, 'Data Analyst',         'Chicago',        71000.00),
(14, 'Liam Anderson',     '2022-05-15', 41, 'Project Manager',      'Houston',        92000.00),
(15, 'Mia Clark',         '2023-03-20', 25, 'Intern',               'Miami',          32000.00);


```sql
SELECT * FROM employees;
| Employee_id | Employee_Name     | Joining_date | Age | Role                | Location      | Salary   |
| ----------- | ----------------- | ------------ | --- | ------------------- | ------------- | -------- |
| 1           | John Smith        | 2020-01-15   | 30  | Software Engineer   | New York      | 80000.00 |
| 2           | Jane Doe          | 2019-03-22   | 28  | HR Manager          | Los Angeles   | 75000.00 |
| 3           | Alice Johnson     | 2021-06-10   | 35  | Data Analyst        | Chicago       | 70000.00 |
| 4           | Bob Brown         | 2022-02-05   | 40  | Project Manager     | Houston       | 90000.00 |
| 5           | Charlie White     | 2023-05-30   | 26  | Intern              | Miami         | 30000.00 |
| 6           | David Wilson      | 2019-08-12   | 32  | Software Engineer   | Seattle       | 82000.00 |
| 7           | Emily Davis       | 2020-11-20   | 29  | HR Assistant        | San Francisco | 60000.00 |
| 8           | Frank Miller      | 2019-07-15   | 38  | Data Scientist      | Boston        | 95000.00 |
| 9           | Grace Lee         | 2022-03-18   | 31  | Project Coordinator | Denver        | 72000.00 |
| 10          | Henry Garcia      | 2023-01-25   | 27  | Intern              | Austin        | 35000.00 |
| 11          | Isabella Martinez | 2021-04-30   | 34  | Software Engineer   | New York      | 81000.00 |
| 12          | Jack Thompson     | 2020-09-10   | 36  | HR Manager          | Los Angeles   | 77000.00 |
| 13          | Karen Robinson    | 2021-12-05   | 29  | Data Analyst        | Chicago       | 71000.00 |
| 14          | Liam Anderson     | 2022-05-15   | 41  | Project Manager     | Houston       | 92000.00 |
| 15          | Mia Clark         | 2023-03-20   | 25  | Intern              | Miami         | 32000.00 |

