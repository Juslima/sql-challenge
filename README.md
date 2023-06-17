# sql-challenge

# Data Modeling
Tables:
1. Departments: This table represents the departments in the organization. It has two columns: dept_no (department number) and dept_name (department name).
2. Employees: This table represents the employees in the organization. It includes columns such as emp_no (employee number), emp_title_id (employee title identifier), birth_date, first_name, last_name, sex, and hire_date.
3. Dept_emp: This table establishes a many-to-many relationship between employees and departments. It has two columns: emp_no and dept_no, serving as foreign keys referencing the respective columns in the Employees and Departments tables.
4. Dept_managers: This table represents the department managers. It includes two columns: dept_no and emp_no, which are foreign keys referencing the Departments and Employees tables, respectively.
5. Salaries: This table stores employee salaries. It has two columns: emp_no, which is a foreign key referencing the Employees table, and salary.
6. Titles: This table stores employee titles. It includes two columns: title_id and title.
   
# Data Engineering

The given data represents a series of SQL queries used to create and describe the structure of database tables. I will go through each query and explain what it does:

1. Create table departments:
   - This query creates a table named "departments" with two columns: "dept_no" and "dept_name".
   - The "dept_no" column is of type VARCHAR(10), which means it can store up to 10 characters.
   - The "dept_name" column is of type VARCHAR(30), which can store up to 30 characters.
   - The "dept_name" column is specified as "NOT NULL", which means it must have a value.
   - The "dept_no" column is defined as the primary key of the table, ensuring its uniqueness.

2. Select * from departments:
   - This query retrieves all rows from the "departments" table.

3. Create table employees:
   - This query creates a table named "employees" with several columns such as "emp_no", "emp_title_id", "birth_date", "first_name", "last_name", "sex", and "hire_date".
   - The "emp_no" column is of type INT and is specified as "NOT NULL".
   - The "emp_title_id" column is of type VARCHAR(20) and is specified as "NOT NULL".
   - The "birth_date", "first_name", "last_name", "sex", and "hire_date" columns are also specified as "NOT NULL".
   - The "emp_no" column is defined as the primary key of the table, ensuring its uniqueness.

4. Select * from employees:
   - This query retrieves all rows from the "employees" table.

5. Create table dept_emp:
   - This query drops an existing table named "dept_emp" if it exists (in case it was created previously).
   - Then it creates a new table named "dept_emp" with two columns: "emp_no" and "dept_no".
   - Both columns are specified as "NOT NULL".
   - The "emp_no" column is a foreign key referencing the "emp_no" column in the "employees" table.
   - The "dept_no" column is a foreign key referencing the "dept_no" column in the "departments" table.

6. Select * from dept_emp:
   - This query retrieves all rows from the "dept_emp" table.

7. Create table dept_managers:
   - This query drops an existing table named "dept_managers" if it exists (in case it was created previously).
   - Then it creates a new table named "dept_managers" with two columns: "dept_no" and "emp_no".
   - Both columns allow NULL values.
   - The "dept_no" column is a foreign key referencing the "dept_no" column in the "departments" table.
   - The "emp_no" column is a foreign key referencing the "emp_no" column in the "employees" table.

8. Select * from dept_managers:
   - This query retrieves all rows from the "dept_managers" table.

9. Create table salaries:
   - This query creates a table named "salaries" with two columns: "emp_no" and "salary".
   - Both columns are specified as "NOT NULL".
   - The "emp_no" column is a foreign key referencing the "emp_no" column in the "employees" table.

10. Select * from salaries:
    - This query retrieves all rows from the "salaries" table.

11. Create table titles:
    - This query creates a table named "titles" with two columns: "title_id" and "title".
    - Both columns are specified as "NOT NULL".

12. Select * from titles:
    - This query retrieves all rows from the "titles" table.

These queries define the structure of several tables and establish relationships (foreign keys) between them. The tables include information about departments, employees, department-employee relationships, department managers, employee salaries, and employee titles.

# Data Analysis

The given data consists of multiple SQL queries that retrieve specific information from a database. I will explain each query and its purpose:

1. List the employee number, last name, first name, sex, and salary of each employee:
   - This query retrieves data from the "employees" and "salaries" tables.
   - It uses a LEFT JOIN to combine the two tables based on the "emp_no" column.
   - The SELECT statement specifies the columns to be displayed: emp_no, last_name, first_name, sex, and salary.
   - The result is ordered by the employee number.

2. List the first name, last name, and hire date for the employees who were hired in 1986:
   - This query retrieves data from the "employees" table.
   - It uses the WHERE clause to filter the employees who were hired in 1986.
   - The SELECT statement specifies the columns to be displayed: first_name, last_name, and hire_date.
   - The result is ordered by the employee number.

3. List the manager of each department along with their department number, department name, employee number, last name, and first name:
   - This query retrieves data from the "dept_managers", "departments", and "employees" tables.
   - It uses multiple LEFT JOINs to combine the tables based on their relationships.
   - The SELECT statement specifies the columns to be displayed from each table.
   - The result is ordered by the employee number.

4. List the department number for each employee along with that employee's employee number, last name, first name, and department name:
   - This query retrieves data from the "employees", "dept_emp", and "departments" tables.
   - It uses multiple INNER JOINs to combine the tables based on their relationships.
   - The SELECT statement specifies the columns to be displayed from each table.
   - The result is ordered by the employee number.

5. List the first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B:
   - This query retrieves data from the "employees" table.
   - It uses the WHERE clause to filter employees based on their first and last names.
   - The SELECT statement specifies the columns to be displayed: first_name, last_name, and sex.

6. List each employee in the Sales department, including their employee number, last name, and first name:
   - This query retrieves data from the "employees", "dept_emp", and "departments" tables.
   - It uses multiple JOINs to combine the tables based on their relationships.
   - The WHERE clause filters employees based on the department name.
   - The SELECT statement specifies the columns to be displayed: emp_no, last_name, and first_name.

7. List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name:
   - This query is similar to the previous one but includes multiple department names in the WHERE clause.

8. List the frequency counts, in descending order, of all the employee last names (i.e., how many employees share each last name):
   - This query retrieves data from the "employees" table.
   - It uses the GROUP BY clause to group the data by last_name.
   - The SELECT statement specifies the last_name column and uses the COUNT(*) function to count the occurrences of each last name.
   - The result is ordered by the frequency count in descending order.

These queries provide different views of the employee data, allowing you to retrieve specific information based on conditions and relationships within the database tables.
