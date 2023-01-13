---Creating a database called Information---
CREATE DATABASE INFORMATION
USE INFORMATION


```python
--Creating a table called EmployeeDemographics---
CREATE TABLE EmployeeDemographics
(EmployeeID int,
FirstName varchar(50),
LastName varchar(50),
Age int,
Gender varchar(50)
)
```


```python
--Creating a table called EmployeeSalary---
CREATE TABLE EmployeeSalary
(EmployeeID int,
JobTitle varchar(50),
Salary int)
```


```python
---Inserting values into EmployeeDemographics----
INSERT INTO EmployeeDemographics VALUES
(1002, 'Pam', 'Beasley', 30, 'Female'),
(1003, 'Dwight', 'Schrute', 29, 'Male'),
(1004, 'Angela', 'Martin', 31, 'Female'),
(1005, 'Toby', 'Flenderson', 32, 'Male'),
(1006, 'Michael', 'Scott', 35, 'Male'),
(1007, 'Meredith', 'Palmer', 32, 'Female'),
(1008, 'Stanley', 'Hudson', 38, 'Male'),
(1009, 'Kevin', 'Malone', 31, 'Male')
```


```python
---Inserting values into EmployeeSalary----
Insert into EmployeeSalary Values
(1002, 'Receptionist',36000),
(1003, 'Salesman',63000),
(1004, 'Accountant',47000),
(1005, 'HR',50000),
(1006, 'Regional Manager',65000),
(1007, 'Supplier Relations',41000),
(1008, 'Salesman',48000),
(1009, 'Accountant',42000)
```


```python
-- Select query to retrieve all records from both tables--
Select * from EmployeeDemographics
Select * from EmployeeSalary
```


```python
--SELECTING THE EMPLOYEE WITH THE MAXIMUM SALARY--
select EmployeeID, Salary from EmployeeSalary
where Salary=(select max(Salary) from EmployeeSalary)
```


```python
--SELECTING THE EMPLOYEE WITH THE 2ND MAXIMUM SALARY--
select TOP 1 EmployeeID, Salary from EmployeeSalary
where Salary<(select max(Salary) from EmployeeSalary)

```


```python
--SQL AND STATEMENT,BOTH STATEMENT MUST BE TRUE TO RETURN RECORDS---
Select * 
from EmployeeDemographics
where Age <= 32 AND Gender='Male'
```


```python
--SQL OR STATEMENT,ONE STATEMENT MUST BE TRUE TO RETURN RECORDS---
Select * 
from EmployeeDemographics
where Age <= 32 OR Gender='Male'

```


```python
--SQL BETWEEN STATEMENT INCLUDES THE END POINTS---
Select * 
from EmployeeDemographics
where Age BETWEEN 29 AND 32

```


```python
--RETRIEVING RECORDS FOR ONLY FEMALES--
Select * 
from EmployeeDemographics
where Gender='Female'
```


```python
--SQL FOR FIRST NAME STARTING WITH a----
Select * 
from EmployeeDemographics
where FirstName LIKE 'a%'
```


```python
--SQL FOR FIRST NAME INCLUDING a----
Select * 
from EmployeeDemographics
where FirstName LIKE '%a%'
```


```python
--SQL FOR FIRST NAME ENDING a----
Select * 
from EmployeeDemographics
where FirstName LIKE '%a'

```


```python
--SQL IN STATEMENT GIVES YOU ALL RECORD A SPECIFIED POSITION OF INTEREST--
Select * from EmployeeDemographics
Where FirstName IN ('Angela','Kevin')
```


```python
--SQL VARIOUS JOIN STATEMENTS---
Insert into EmployeeDemographics values
(NULL,'Holly','Flax',NULL,NULL)
Insert into EmployeeDemographics values
(1013,'Darryl','Philbin',NULL,'Male')
select * from EmployeeDemographics
```


```python
Insert into EmployeeSalary values
(1010,NULL,47000),
(NULL,'Salesman',43000)
select * from EmployeeSalary
```


```python
Insert into EmployeeSalary values
(1010,NULL,47000),
(NULL,'Salesman',43000)
select * from EmployeeSalary
```


```python
--SQL RIGHT JOIN--
select ES.EmployeeID,ED.FirstName,ED.LastName,ES.JobTitle,ES.Salary
from EmployeeDemographics AS ED
RIGHT JOIN EmployeeSalary AS ES
ON ED.EmployeeID=ES.EmployeeID
```


```python
--SQL FULL OUTER JOIN---
select ED.EmployeeID,ED.FirstName,ED.LastName,ES.JobTitle,ES.Salary
from EmployeeDemographics AS ED 
FULL OUTER JOIN EmployeeSalary AS ES
ON ED.EmployeeID=ES.EmployeeID
```


```python
--SQL JOIN---
select ED.EmployeeID,ED.FirstName,ED.LastName,ES.JobTitle,ES.Salary
from EmployeeDemographics AS ED
JOIN EmployeeSalary AS ES
ON ED.EmployeeID=ES.EmployeeID
```
