<div class="top">

# Querying table "ratings_by_user"
### [◂](command:katapod.loadPage?step5){.steps} Step 6 of 11 [▸](command:katapod.loadPage?step7){.steps}
</div>

Table `ratings_by_user` stores information about movie ratings organized by users, 
such that each partition contains all ratings left by one particular user.
This table has multi-row partitions and 
the primary key defined as `PRIMARY KEY ((email), title, year)`. 
Let's first retrieve all rows from the table to learn how the data looks like and then focus 
on predicates that the primary key can support.

Q1. Retrieve all rows:
```
SELECT * FROM ratings_by_user;
```

Q2. Retrieve one partition:
```
SELECT * FROM ratings_by_user
WHERE email = 'joe@datastax.com';
```

Q3. Retrieve two partitions:
```
SELECT * FROM ratings_by_user
WHERE email IN ('joe@datastax.com',
                'jen@datastax.com');
```

Q4. Retrieve one row:
```
SELECT * FROM ratings_by_user
WHERE email = 'jim@datastax.com'
  AND title = 'Alice in Wonderland'
  AND year  = 2010;
```

Q5 - Q8. Retrieve a subset of rows from a partition:
```
SELECT * FROM ratings_by_user
WHERE email = 'jim@datastax.com'
  AND title = 'Alice in Wonderland'
  AND year IN (2010, 1951);
```
```
SELECT * FROM ratings_by_user
WHERE email = 'jim@datastax.com'
  AND title = 'Alice in Wonderland'
  AND year  > 1950;
```
```
SELECT * FROM ratings_by_user
WHERE email = 'jim@datastax.com'
  AND title = 'Alice in Wonderland';
```
```
SELECT * FROM ratings_by_user
WHERE email = 'jim@datastax.com'
  AND title < 'Charlie and the Chocolate Factory';
```

[continue](command:katapod.loadPage?step7){.orange_bar}