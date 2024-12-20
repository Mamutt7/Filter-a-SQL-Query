# Filter-a-SQL-Query

As a security analyst, knowing how to make better queries to retrieve specific pieces of data can help you find the security-related information you need more efficiently.

In this lab activity, you’ll apply basic filters to SQL queries to retrieve information from a MariaDB database.

## Scenario
In this scenario, you need to get specific information about employees, their machines, and the departments they’re in. Your team needs this data to perform various tasks, such as running updates, posting a privacy notice in certain departments, and sending an alert to an employee with an issue on a machine.

You are responsible for finding the required information by querying a database. You’ll add filters to your queries to locate the information more quickly.

Here’s how you’ll do this task: First, you’ll list all organization machines and their operating systems. Second, you’ll list all machines with the operating system OS 2. Third, you’ll list all the employees in the Finance and Sales departments. Fourth, you’ll obtain information about machines.

### Task 1. List all organization machines
In this task, you need to get a list of all organization machines and their operating systems. The data is contained in the `machines table`. You’ll need to use the `SELECT` keyword to return specific columns.

- Run a SQL query to retrieve only the `device_id` and `operating_system` columns from the `machines` table.

![image](https://github.com/user-attachments/assets/187bb41c-b778-48cb-ab2b-3cbab501c6e6)


### Task 2. Retrieve a list of the machines with OS 2
In this task, you need to obtain a list of all machines with the `'OS 2'` operating system because these machines need an update. To get this information, you’ll run your first SQL query with a filter.

- Select all the records from the machines table with a value of `'OS 2'` in the operating_system column. Replace the value X with the correct string:

```
SELECT device_id, operating_system
FROM machines 
WHERE operating_system = 'X';
```

![image](https://github.com/user-attachments/assets/5ff394f9-553a-4911-90fb-ae836a2385d0)


### Task 3. List employees in specific departments
In this task, you need to retrieve a list of all the employees in the Finance and Sales departments to obtain their office numbers. A notice about handling confidential financial information will be posted to these offices.

1. Filter the rows returned from `department` column in the `employees` table to include only employees from the `'Finance'` department. Replace `X` with the appropriate column name and `Y` with the appropriate value to complete the filter:

```
SELECT * 
FROM employees 
WHERE X = 'Y';
```

![image](https://github.com/user-attachments/assets/6bba1f04-314a-4ebb-beb4-e31aa626987c)


2. Modify the previous query so that it returns employees who are in the `'Sales'` department.

![image](https://github.com/user-attachments/assets/7cb68319-a44a-4770-a892-b030c0945aae)


### Task 4. Identify employee machines
Your team recently discovered that there are issues with machines in the South building. In this task, you need to obtain certain employee and computer information.

A machine in `'South-109'` has an issue. You need to determine which employee uses that computer so you can send them an alert.

1. Write a query to identify which employee uses the office in `'South-109'`. (The data must be returned from the `office` column in the `employees` table.)

![image](https://github.com/user-attachments/assets/7ebf84eb-16b5-4508-9279-a160ff6ab519)

Next, your team has determined that there is an issue with all the machines in the South building. Offices in the organization are named with the building name, a hyphen, and the office number in that building (for example, `'South-109'`).

2. Modify the query you used in the previous step so that it returns information on all the employees in the `'South'` building. Use the `LIKE` operator with `%` in this query.

![image](https://github.com/user-attachments/assets/21ef950c-735f-4e33-99a8-871da54fca70)
