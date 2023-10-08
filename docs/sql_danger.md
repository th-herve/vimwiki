# Sql danger

## SQL Injection Attack

SQL injection attacks can be prevented by using parameterized queries or prepared statements.
Avoid using user input directly in SQL queries, as it can allow malicious code to be executed.

## Race condition

If a lot of operation  are executed at the same time they can interfere each others.

Ex: everybody like a post on instagram at the same time, instead of going from 100 likes to 103, 101 can be registered 2 times and we get 102

Solution: 

- BEGIN TRANSACTION
- COMMIT
- ROLLBACK
- (LOCKING) not used a lot
