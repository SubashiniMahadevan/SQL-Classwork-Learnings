# SQL-Classwork-Learnings

# Data Analysis Using SQL - World Database **

**1. Using count, get the number of cities in the USA**

**use world;**

**show tables;**

**2. SELECT COUNT(DISTINCT Name) AS USA_city_count FROM city WHERE CountryCode='USA' GROUP BY CountryCode;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/b5e58705-f24e-4665-8a51-788159ca53e1)

**3. Using ORDER BY, LIMIT, what country has the highest life expectancy?**

**use world;**

**show tables;**

**SELECT Name,LifeExpectancy FROM country ORDER BY LifeExpectancy DESC LIMIT 1;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/78525c05-91a5-40bf-abb7-57ddca031a1d)


**4. Find Average Life Expectancy and Population of ARGENTINA**

**use world;**

**show tables;**

**SELECT * FROM country;**

**SELECT Name,Code,Population,round(AVG(LifeExpectancy),0) AS Avg_Life_Exp FROM country WHERE Code='ARG' GROUP BY Code;**


![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/11711bc0-1637-4ffc-a6c3-d0d54061754b)

**5. Select 25 cities around the world that start with the letter 'F' in a single SQL query.**

**use world;**

**show tables;**

**SELECT Name FROM city WHERE Name LIKE 'F%' LIMIT 25;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/c9ca239b-4737-4d02-90e8-7bf440d84cd8)


**6. Create a SQL statement to display columns Id, Name, Population from the city table and limit results to first 10 rows only.**

**use world;**

**show tables;**

**7. SELECT ID,Name,Population FROM city LIMIT 10;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/ae11a9ba-5793-4ba9-9629-2d6ed8a0dc7b)

**7. Create a SQL statement to display columns Id, Name, Population from the city table and limit results to rows 31-40.**

**use world;**

**show tables;**

**8. SELECT ID,Name,Population FROM city ORDER BY ID LIMIT 30, 10;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/e9bf0f59-310c-498b-9953-2ec5e936a59a)


**9. Create a SQL statement to find only those cities from city table whose population is larger than 2000000.**

**use world;**

**show tables;**

**10. SELECT Id,Name,Population FROM city WHERE Population>2000000 ORDER BY Population;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/c514a553-1a5b-4c05-b4b3-69e556c0d920)


**11. Create a SQL statement to find all city names from city table whose name begins with 'Be' prefix.**

**use world;**

**show tables;**

**SELECT Name FROM city WHERE Name LIKE "Be%";**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/c93bac89-3bcd-4bab-bc31-fe01e2e1a9ab)


**12. Create a SQL statement to find only those cities from city table whose population is between 500000-1000000.**

**use world;**

**show tables;**

**SELECT Name,Population FROM city WHERE Population BETWEEN 500000 AND 1000000 ORDER BY Population;**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/376508f3-b506-46b7-affb-ded9be261ac0)

** using JOINS**

**1. Create a SQL statement to find the capital of Spain (ESP).**

**use world;**

**show tables;**

**SELECT co.Name AS Country,c.CountryCode,c.Name AS Capital,co.Capital FROM country AS co INNER JOIN city AS c ON c.ID=co.Capital AND co.Code='ESP';**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/e8d98937-49e8-410b-8137-4ec5d2ab524a)

**use world;**

**show tables;**

**2. Create a SQL statement to find the country with the highest life expectancy.**

** Instead Of Sub Queries using Joins for increasingthe performance of the Query**

**use world;**

**show tables;**

**SELECT c1.Name AS Country_high_life_expectancy,c1.LifeExpectancy FROM country AS c1 JOIN (SELECT Max(LifeExpectancy) AS life FROM country) AS c2 ON c1.LifeExpectancy = c2.life;**


![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/394429aa-9abf-4acc-865e-87f592850bfe)


**3.	Create a SQL statement to find all cities from the Europe continent.**

**use world;**

**show tables;**

**SELECT DISTINCT c.Name AS Cities_in_Europe FROM city AS c INNER JOIN country AS co ON c.CountryCode=co.Code AND co.Continent='Europe';**

![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/496e3a15-7ae0-4254-9b85-28b86e8cbae6)


**4. Create a SQL statement to find the most populated city in the city table.**

**use world;**

**show tables;**

**SELECT c.name FROM city AS c LEFT JOIN city AS c1 ON c.Population < c1.Population WHERE c1.Population IS NULL;**


![image](https://github.com/SubashiniMahadevan/SQL-Classwork-Learnings/assets/168095179/a5ff3289-b7d7-49e8-848f-0afa70e9f03b)














