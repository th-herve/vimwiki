# Sql query example


```sql
-- Select min and max city name length, uses two query  

SELECT city, length(city)
FROM station
WHERE length(city) = (SELECT MIN(length(city))
                        FROM station)
ORDER BY city
LIMIT 1;

SELECT city, length(city)
FROM station
WHERE length(city) = (SELECT MAX(length(city))
                        FROM station)
ORDER BY city
LIMIT 1;

-- City that start with a vowel                                     TAGS: REGEX

SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[aeiou]';

-- City that starts and ends with vowel                             TAGS: REGEX
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[aeiou].*[aeiou]$';

-- Student who score more that 75, ordered by the LAST three        TAGS: REGEX
-- letter of their name and if the same, the id

SELECT name
FROM students
WHERE marks > 75
ORDER BY RIGHT(name, 3), id;

-- Print triangle properties based on A, B, C side length           TAGS: CONDITIONAL, IF, IF..ELSE

SELECT 
    CASE
        -- test if triangle 
        WHEN ( A + B > C
           AND A + C > B
           AND B + C > A) THEN 
                CASE 
                    -- test if equilateral or scalene, else it's isocles
                    WHEN A = B AND B = C THEN 'Equilateral'
                    WHEN A != B AND B != C AND C != A THEN 'Scalene'
                    ELSE 'Isosceles'
                END
        else 'Not A Triangle'
    END AS triangle_type
FROM TRIANGLES;

-- select the name immediately followed by its profession's first letter.

SELECT 
    CASE
      WHEN occupation = "Doctor" THEN CONCAT(name, "(D)")
      WHEN occupation = "Professor" THEN CONCAT(name, "(P)")
      WHEN occupation = "Singer" THEN CONCAT(name, "(S)")
      WHEN occupation = "Actor" THEN CONCAT(name, "(A)")
    END AS occupation
FROM occupations
ORDER BY name;

-- Print the number of person for each profession formatted

SELECT CONCAT("There are a total of ", COUNT(occupation)," ", LOWER(occupation), "s.")
FROM occupations
GROUP BY occupation
ORDER BY COUNT(occupation), occupation;
```
