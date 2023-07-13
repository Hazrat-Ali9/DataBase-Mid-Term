# Question No : 1  
# Create the employee table without constraints
# Answer No : 1

CREATE TABLE employee (
	employee_id INT,
	first_name VARCHAR(20),
	last_name VARCHAR(25),
	email	VARCHAR(25),
	phone_number VARCHAR(20),
	hire_date DATE,
	job_id VARCHAR(10),
	salary DECIMAL (8,2)
);

# Question No : 2
# Create the employee table with proper constraints.
# Answer No : 2
CREATE TABLE employee (
	employee_id INT UNSIGNED NOT NULL,
	first_name VARCHAR(20),
	last_name VARCHAR(25) NOT NULL,
	email	VARCHAR(25) NOT NULL,
	phone_number VARCHAR(20),
	hire_date DATE NOT NULL,
	job_id VARCHAR(10) NOT NULL,
	salary DECIMAL (8,2) NOT NULL
);


# Question No : 3 
# Show all of employee table											     
# Answer No : 3
SELECT * FROM employee;
                                   
# Question No : 4
# Show the first names and salaries of employee who has last name “king”
# Answer No : 4
SELECT first_name, salary
FROM employee
WHERE last_name LIKE '%King%';

# Question No : 5
# Show the first names and last names of the employees who has salary greater than 200
# Answer No : 5

SELECT first_name, last_name
FROM employee
where salary > 2000;


# Question No : 6
# Show the employee names and salaries who earns more than average salary.	             
# Answer No : 6
SELECT first_name, last_name, salary
FROM employee
WHERE salary > (SELECT AVG(salary) FROM employees);


# Question No : 7 				          
# Group the employees using job id and show the average and max salary of each job id. 
# Answer No : 7

SELECT job_id, AVG(salary), MAX(salary)
FROM employee
GROUP BY job_id;


# Question No : 8                                                          
# Sort the employee table ascending order according to salary and show 5th to 10th rows.
# Answer No : 8
SELECT *
FROM employee
ORDER BY salary ASC
LIMIT 6 offset 4;


# Question No. 09 
# Count the employees and total salary.  
# Answer No : 9

SELECT COUNT(*), SUM(salary)
FROM employee;
 
 
 







 
 







