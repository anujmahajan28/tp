-- Display the structure of the Departments table
DESC Departments;

-- Select all rows from the Departments table
SELECT * FROM Departments;

-- Display the structure of the Employees table
DESC Employees;

-- SQL query to retrieve specific columns from Employees table
SELECT employee_id, first_name, last_name, job_id, hire_date, department_id, salary 
FROM Employees;


SELECT DISTINCT department_id, job_id 
FROM Employees;


SELECT 
    last_name || ' - ' || job_id AS Employees,
    job_id,
    salary,
    ((salary + 500) * 12) AS "Annual Compensation"
FROM Employees;
