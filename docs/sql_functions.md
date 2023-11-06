# Sql functions


## Date

### GETDATE()

```sql
SELECT GETDATE();
```
### DATEPART()

Return a specific part of a date.

```sql
SELECT DATEPART(year, '2017/08/25') AS YearOnly;
```
| field       | argument           |
|-------------|--------------------|
| year        | year, yyyy, yy     |
| month       | month, mm, m       |
| day         | day, dd, d         |
| hour        | hour, hh           |
| minute      | minute, mm, m      |
| second      | second, ss, s      |
| millisecond | millisecond, ms    |

## Conversion

- TO_HEX()
- TO_BINARY / TO_BINARY_DOUBLE / TO_BINARY_FLOAT
- TO_CHAR()
- TO_DATE/TO_TIMESTAMP
- TO_NUMBER

## Rounding

- FLOOR()
- CEILING()
- ROUND(number, decimal)

## String

- STRING_SPLIT (string, separator)
