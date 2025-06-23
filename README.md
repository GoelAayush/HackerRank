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

# Weather Observation Station 2
SELECT ROUND(SUM(LAT_N),2) AS Latitude, ROUND(SUM(LONG_W),2) AS Longitude
FROM STATION;

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

# Weather Observation Station 13
SELECT ROUND(SUM(LAT_N),4) AS Latitude
FROM STATION
WHERE LAT_N BETWEEN 38.7880 AND 137.2345;

# Weather Observation Station 14
SELECT ROUND(MAX(LAT_N),4)
FROM STATION
WHERE LAT_N < 137.2345;

# Weather Observation Station 15
SELECT ROUND(LONG_W,4) AS Longitude 
FROM STATION
WHERE LAT_N = (SELECT MAX(LAT_N) 
               FROM STATION
              WHERE LAT_N < 137.2345
              ); 

# Weather Observation Station 16
SELECT ROUND(MIN(LAT_N),4) AS Latitude
FROM STATION
WHERE LAT_N > 38.7780;

# Weather Observation Station 17
SELECT ROUND(LONG_W,4) AS Longitude
FROM STATION
WHERE LAT_N = (SELECT MIN(LAT_N) FROM STATION
              WHERE LAT_N > 38.7780
              );

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
FROM TRIANGLES;

# Revising Aggregations - The Count Function
SELECT COUNT((DISTRICT)) FROM CITY
WHERE POPULATION > 100000;

# Average Population
SELECT ROUND(AVG(POPULATION)) AS Avg_POP FROM CITY ;

# Japan Population
SELECT SUM(POPULATION) FROM CITY 
WHERE COUNTRYCODE = 'JPN';

# Population Density Difference
SELECT MAX(POPULATION) - MIN(POPULATION) AS POP
FROM CITY;

# The Blunder
SELECT CEIL(AVG(SALARY) - AVG(CAST(REPLACE(Salary,'0','')AS UNSIGNED)))
FROM EMPLOYEES;

# Top Earners
SELECT CONCAT(MAX(Earning),' ', COUNT(Earning))
FROM (
SELECT (salary * months) AS Earning 
FROM Employee
) AS Final
WHERE Earning = (SELECT MAX(salary * months) FROM Employee);

# Population Census
SELECT SUM(a.POPULATION) 
FROM CITY AS a
LEFT JOIN COUNTRY AS b
ON a.COUNTRYCODE = b.CODE
WHERE b.CONTINENT = 'Asia';

# African Cities
SELECT a.NAME
FROM CITY AS a
LEFT JOIN COUNTRY AS b
ON a.COUNTRYCODE = b.CODE
WHERE CONTINENT = 'Africa';

# Average Population of Each Continent
SELECT b.CONTINENT, FLOOR(AVG(a.POPULATION)) AS POP
FROM COUNTRY AS b
JOIN CITY AS a
ON b.CODE = a.COUNTRYCODE
GROUP BY b.CONTINENT;

# Revising Aggregations - The Sum Function
SELECT SUM(POPULATION) 
FROM CITY
WHERE District = 'California';








