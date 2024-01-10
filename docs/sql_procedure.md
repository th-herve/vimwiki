# Procedure

Create a callable set of sql instruction that can take arguments.

```sql
CREATE PROCEDURE insert_student
    @name varchar,
    @house_id int,
AS
BEGIN
  INSERT INTO student (name, house) VALUES (@name, @house_id);
END

-- then call it
EXECUTE insert_student @name = 'Ron', @house_id = 1;
```
