# SQL-Queries

## Scenario:
### Perform SQL queries to create tables and extract meaningful information from a Student and Course database.

## CODE:
```sql
CREATE TABLE Student (
RollNo INT PRIMARY KEY,
Name VARCHAR(100) NOT NULL,
Marks DECIMAL(5, 2) NOT NULL,
AadharNumber CHAR(12) UNIQUE NOT NULL,
Address VARCHAR(255)
);
CREATE TABLE Course (
RollNo INT,
Course VARCHAR(100) NOT NULL,
Course_Duration VARCHAR(50),
FOREIGN KEY (RollNo) REFERENCES Student(RollNo)
);
INSERT INTO Student (RollNo, Name, Marks, AadharNumber, Address)
VALUES
(1, 'John Doe', 85.5, '123456789012', '123 Elm Street'),
(2, 'Rane Smith', 25.0, '987654321098', '456 Oak Avenue'),
(3, 'Alice Johnson', 78.0, '111223344556', '789 Pine Road');
INSERT INTO Course (RollNo, Course, Course_Duration)
VALUES
(1, 'BCA', '6 months'),
(1, 'MBA', '6 months'),
(2, 'BBA', '6 months'),
(3, 'BCA', '6 months');

SELECT AVG(Marks) AS AverageMarks

FROM Student;
SELECT Name
FROM Student
ORDER BY Name ASC;
SELECT RollNo, Name

FROM Student
WHERE Marks < 30;
SELECT RollNo
FROM Student
WHERE Name LIKE 'R%';
SELECT DISTINCT RollNo
FROM Course
WHERE Course = 'BCA';

Output:

AverageMarks                            
----------------------------------------
                               62.833333
Name                                                                                                
----------------------------------------------------------------------------------------------------
Alice Johnson                                                                                       
John Doe                                                                                            
Rane Smith                                                                                          
RollNo      Name                                                                                                
----------- ----------------------------------------------------------------------------------------------------
          2 Rane Smith                                                                                          
RollNo     
-----------
          2
RollNo     
-----------
          1
          3
