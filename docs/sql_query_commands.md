# Query command

## AVG

Give the average.

```sql
SELECT AVG(grade)
FROM grades;
```

## COUNT

```sql
SELECT COUNT(*) FROM student;

SELECT COUNT(DISTINCT(car_model)) from car;
```

used with distinct, it will not count duplicate.

## LOWER/UPPER

String function that convert character to lower/upper case

```sql
SELECT UPPER(name) FROM student;
SELECT LOWER(name) FROM student;
```

## MIN/MAX

Return the min/max value from a column. Also work with string (return based on the number of character).

```sql
SELECT MAX(grade) FROM grade;
```
