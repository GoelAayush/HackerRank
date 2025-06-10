# HackerRank SQL Answers

# Revising the Select Query I
SELECT * FROM CITY WHERE COUNTRYCODE = "USA"
AND POPULATION > 100000;

# Revising the Select Query II
SELECT NAME FROM CITY
WHERE COUNTRYCODE = "USA" AND POPULATION > 120000;

# Select All
SELECT * FROM CITY;

# Select By ID
SELECT * FROM CITY
WHERE ID = 1661;

# Japanese Cities' Attributes
SELECT * FROM CITY 
WHERE COUNTRYCODE = "JPN";

# Japanese Cities' Names
SELECT NAME FROM CITY WHERE COUNTRYCODE = "JPN";

# Weather Observation Station 1
SELECT CITY, STATE FROM STATION;

# Weather Observation Station 3
SELECT CITY FROM STATION WHERE ID % 2 = 0
GROUP BY CITY
ORDER BY CITY;

# Weather Observation Station 4
SELECT COUNT(ID) - COUNT(DISTINCT(CITY)) FROM STATION;

# Weather Observation Station 5
(SELECT CITY, LENGTH(CITY) AS Length FROM STATION
ORDER BY LENGTH(CITY), CITY
LIMIT 1)
UNION ALL
(
SELECT CITY, LENGTH(CITY) AS Length FROM STATION
ORDER BY LENGTH(CITY) Desc, CITY
LIMIT 1);

# Weather Observation Station 6
SELECT DISTINCT CITY FROM STATION
WHERE LEFT(CITY,1) IN ('a','e','i','o','u');

# Weather Observation Station 7
SELECT CITY FROM STATION
WHERE RIGHT(CITY,1) IN ('a','e','i','o','u')
GROUP BY CITY;

# Weather Observation Station 8
SELECT CITY FROM STATION 
WHERE LEFT(CITY,1) IN ('a','e','i','o','u')
AND RIGHT(CITY,1) IN ('a','e','i','o','u')
GROUP BY CITY;

# Weather Observation Station 9
SELECT CITY FROM STATION 
WHERE LEFT(CITY,1) NOT IN ('a','e','i','o','u')
GROUP BY CITY;

# Weather Observation Station 10
SELECT CITY FROM STATION 
WHERE RIGHT(CITY,1) NOT IN ('a','e','i','o','u')
GROUP BY CITY;

# Weather Observation Station 11
SELECT CITY FROM STATION 
WHERE LEFT(CITY,1) NOT IN ('a','e','i','o','u')
OR RIGHT(CITY,1) NOT IN ('a','e','i','o','u')
GROUP BY CITY;

# Weather Observation Station 12
SELECT CITY FROM STATION 
WHERE LEFT(CITY,1) NOT IN ('a','e','i','o','u')
AND RIGHT(CITY,1) NOT IN ('a','e','i','o','u')
GROUP BY CITY;

# Higher Than 75 Marks
SELECT Name FROM STUDENTS
WHERE Marks > 75
ORDER BY RIGHT(Name,3), ID;

# Employee Names
SELECT name FROM Employee
ORDER BY name;

# Employee Salaries
SELECT name FROM Employee WHERE salary > 2000
AND months < 10
ORDER BY employee_id;

# Type of Triangle
SELECT CASE
WHEN A + B <= C OR B+C <= A OR A+C <= B THEN 'Not A Triangle'
WHEN A=B AND A=C THEN 'Equilateral'
WHEN A=B OR B=C OR A=C THEN 'Isosceles'
ELSE 'Scalene'
END AS Type_of_Triangle
FROM TRIANGLES








