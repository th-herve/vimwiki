# Sql conditional

Sql support conditional statements with the `CASE` `WHEN` and `ELSE` keywords.
`!!` Not WHERE

```sql
-- select if student passed or not
SELECT name,
  CASE 
    WHEN grade > 16 THEN 'Passed, great !'
    WHEN grade > 10 THEN 'Passed'
    ELSE 'Failed'
  -- end the case and set alias
  END AS passed
FROM students
```

Can be nested

```sql
SELECT
  CASE 
    WHEN is_student THEN
      CASE
        WHEN grade > 10 THEN 'Passed'
        ELSE 'Failed'
      END
    ELSE 'Not a student'
  END AS passed
FROM students
```
